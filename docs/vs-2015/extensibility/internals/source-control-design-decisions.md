---
title: Entwurfsentscheidungen bei der Datenquelle | Microsoft-Dokumentation
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
- source control [Visual Studio SDK], design decisions
ms.assetid: 5f60ec1a-5a74-4362-8293-817a4dd73872
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1f43c9d2423e0eaafbdcae41169c47d5fcb01912
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47510153"
---
# <a name="source-control-design-decisions"></a>Entwurfsentscheidungen bei der Quellcodeverwaltung
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Entwurfsentscheidungen bei der Quelle](https://docs.microsoft.com/visualstudio/extensibility/internals/source-control-design-decisions).  
  
Die folgenden entwurfsentscheidungen für Projekte berücksichtigen Sie beim Implementieren von Datenquellen-Steuerelement.  
  
## <a name="will-information-be-shared-or-private"></a>Wird Informationen freigegeben oder privat sein?  
 Die wichtigste entwurfsentscheidung, die Sie vornehmen können, ist, welche Informationen freigegeben werden kann und was privat ist. Beispielsweise wird die Liste der Dateien für das Projekt freigegeben, aber in der Liste der Dateien, einige Benutzer möchten private Dateien haben. Compilereinstellungen werden freigegeben, aber das Startprojekt in der Regel privat ist. Einstellungen sind entweder ausschließlich freigegebene, zusammen mit einer Außerkraftsetzung oder rein privat. Programmbedingt private Elemente, wie z. B. Lösung Benutzeroptionen (SUO)-Dateien werden nicht überprüft in [!INCLUDE[vsvss](../../includes/vsvss-md.md)]. Achten Sie darauf, dass Sie keine privaten Informationen in privaten Dateien, z. B. die SUO-Datei oder eine bestimmte private-Datei, die Sie, z. B. erstellen Speichern einer. csproj.user-Datei für Visual c# oder eine. vbproj.user-Datei für Visual Basic.  
  
 Diese Entscheidung ist nicht vollständig und kann auf einer Basis Element-vorgenommen werden.  
  
## <a name="will-the-project-include-special-files"></a>Wird das Projekt, die spezielle Dateien enthalten?  
 Eine weitere wichtige Entscheidung ist, ob Ihre Projektstruktur für spezielle Dateien verwendet. Spezielle Dateien sind ausgeblendet, die die Dateien zugrunde liegen, die sichtbar im Projektmappen-Explorer und in das Einchecken und Auschecken Dialogfelder sind. Wenn Sie spezielle Dateien verwenden, beachten Sie Folgendes:  
  
1.  Ordnen Sie keine Gerätedateien, die die Stammknoten des Projekts, d. h. mit dem Projekt die Datei selbst. Die Projektdatei, muss es sich um eine einzelne Datei sein.  
  
2.  Wenn spezielle Dateien hinzugefügt, entfernt oder umbenannt werden, in einem Projekt auf die entsprechende <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2> müssen Ereignisse ausgelöst werden, wobei das Flag festgelegt, der angibt, die Dateien sind spezielle Dateien. Diese Ereignisse werden von der Umgebung als Reaktion auf das Projekt, das Aufrufen der entsprechenden aufgerufen <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> Methoden.  
  
3.  Wenn das Projekt oder die-Editor aufruft <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> für eine Datei, die speziellen Dateien, die der Datei zugeordneten nicht automatisch ausgecheckt. Übergeben Sie die speziellen Dateien im zusammen mit der übergeordneten Datei. Die Umgebung erkennt die Beziehung zwischen allen Dateien, die übergeben werden und entsprechend der speziellen Dateien in der Benutzeroberfläche Auschecken ausblenden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [Unterstützen der Quellcodeverwaltung](../../extensibility/internals/supporting-source-control.md)

