---
title: Beibehalten von Daten in der MSBuild-Projektdatei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project files, persisting data in
ms.assetid: 6a920cb7-453d-4ffd-af1c-6f3084bd03f7
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 288fe5387a25ed74f0fd18d9d461328f4e922724
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47520835"
---
# <a name="persisting-data-in-the-msbuild-project-file"></a>Beibehalten von Daten in der MSBuild-Projektdatei
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [beibehalten von Daten in der MSBuild-Projektdatei](https://docs.microsoft.com/visualstudio/extensibility/internals/persisting-data-in-the-msbuild-project-file).  
  
Einem Projektuntertyp untertypspezifischen Daten in die Projektdatei für die spätere Verwendung beibehalten werden müssen. Project-Datei-Persistenz wird von einem Projektuntertyp verwendet, um die folgenden Anforderungen erfüllen:  
  
1.  Beibehalten von Daten, die als Teil der Erstellung des Projekts verwendet. (Weitere Informationen auf der Microsoft Build Engine finden Sie unter [MSBuild](http://msdn.microsoft.com/en-us/7c49aba1-ee6c-47d8-9de1-6f29a906e20b).) Auf Builds bezogene Informationen folgende Möglichkeiten:  
  
    1.  Configuration-unabhängige Daten. D. h. Daten, die in MSBuild-Elemente mit leeren oder fehlenden Bedingungen gespeichert.  
  
    2.  Daten, die Konfiguration abhängig. D. h. Daten, die in MSBuild-Elemente, die für einen bestimmten Projektkonfiguration bedingte werden gespeichert. Zum Beispiel:  
  
        ```  
        <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
        ```  
  
2.  Beibehalten von Daten, die für das Erstellen nicht relevant ist. Diese Daten können in der formfreien XML ausgedrückt werden, die nicht mit einem XML-Schema überprüft wird.  
  
    1.  Configuration-unabhängige Daten.  
  
    2.  Daten, die Konfiguration abhängig.  
  
## <a name="persisting-build-related-information"></a>Beibehalten von buildbezogene Informationen  
 Persistenz der Daten für das Erstellen eines Projekts erfolgt mithilfe von MSBuild. Das MSBuild-System verwaltet eine Mastertabelle mit buildbezogene Informationen. Projektuntertypen sind verantwortlich für den Zugriff auf diese Daten zum Abrufen und Festlegen von Eigenschaftswerten. Projektuntertypen können die Datentabelle auf Builds bezogene verbessern, indem zusätzliche Eigenschaften beibehalten werden sollen und Entfernen von Eigenschaften, sodass sie nicht persistent gespeichert werden.  
  
 Um die MSBuild-Daten zu ändern, einem Projektuntertyp dient zum Abrufen der MSBuild-Property-Objekt aus dem System des Projekts über <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> ist eine Schnittstelle, die auf das Core-Projektsystem und die aggregieren Projekt Untertyp Abfragen für es implementiert, indem Sie Ausführung `QueryInterface`.  
  
 Das folgende Verfahren erläutert die Schritte zum Entfernen einer Eigenschaft mithilfe <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage>.  
  
#### <a name="to-remove-a-property-from-an-msbuild-project-file"></a>So entfernen Sie eine Eigenschaft aus einer MSBuild-Projektdatei  
  
1.  Rufen Sie `QueryInterface` auf <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> des projektuntertyps.  
  
2.  Rufen Sie <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.RemoveProperty%2A> mit `pszPropName` Festlegen der Eigenschaft, die Sie entfernen möchten.  
  
### <a name="persisting-non-build-related-information"></a>Beibehalten von nicht mit dem Build-Informationen  
 Dauerhaftigkeit der Daten in Projektdateien, die keine Rolle spielt, Erstellung erfolgt über <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment>.  
  
 Sie implementieren können <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> auf dem hauptblatt `project subtype aggregator` -Objekt, das `project subtype project configuration` Objekt oder beides.  
  
 Die folgenden Punkte beschreiben die wichtigsten Konzepte in Bezug auf die Persistenz nicht mit dem Build-Informationen.  
  
-   Das Basisprojekt aufruft, für das Hauptprojekt Untertyp (d. h. den äußeren Projektuntertyp)-Aggregator-Objekt zum Laden und Speichern von Konfigurationsdaten für unabhängige, und er ruft für den Projekt-Untertyp Projekt Konfigurationsobjekten zum Laden und speichern abhängig von der Konfiguration Daten.  
  
-   Das Basisprojekt Ruft die Methoden von <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> mehrfach für jede Ebene der Aggregation der Projekt-Untertyp, auf, und übergeben Sie die GUID für jede Ebene.  
  
-   Das Basisprojekt übergibt oder erhält ein XML-Fragment, die für ein bestimmtes Projektuntertyp dediziert ist und dieser Mechanismus als Methode für die Beibehaltung des Status zwischen den Aggregationsebenen verwendet.  
  
-   Das Basisprojekt ruft des äußeren projektuntertyps <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment>Implementierung, die eine GUID übergeben. Wenn die GUID der äußeren Projektuntertyp angehört, wird den Aufruf selbst behandelt; andernfalls delegiert sie den Aufruf einer inneren Projektuntertyp usw., bis der Projektuntertyp, dem die GUID entspricht gefunden wird.  
  
-   Einem Projektuntertyp kann auch das XML-Fragment ändern, bevor oder nachdem der Aufruf von einer inneren Projektuntertyp delegiert. Das folgende Beispiel zeigt einen Auszug aus einer Projektdatei, in dem ein Name einer Datei, die Eigenschaften, die spezifisch für einen Projektuntertyp enthält wird an dieser Projektuntertyp.  
  
    ```  
    <ProjectExtensions>  
        <VisualStudio>  
          <FlavorProperties GUID="{<FlavorGUID>}">  
            <FlavorProject TestFileFolder="TestFile" />  
          </FlavorProperties>  
        </VisualStudio>  
      </ProjectExtensions>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Projektuntertypen](../../extensibility/internals/project-subtypes.md)

