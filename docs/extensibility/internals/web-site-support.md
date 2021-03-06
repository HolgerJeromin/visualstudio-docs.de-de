---
title: Der Support-Website | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d3da310c6695598eef36998cc562f6d477eff29
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139850"
---
# <a name="web-site-support"></a>Der Support-Website
Ein Projektsystem Website ist ein Projektsystem, das Webprojekte erstellt. Webprojekte erstellen wiederum Webanwendungen. Ein Website-Projekt generiert eine ausführbare Datei für jede Webseite, die Code verknüpft ist. Zusätzliche ausführbare Dateien werden aus der Quellcodedateien im Ordner "App_Code" generiert.  
  
 Website-Projektsysteme werden durch Hinzufügen von Vorlagen und Registrierungsattribute zu einem vorhandenen Projektsystem erstellt. Eines dieser Attribute wählt der IntelliSense-Anbieter für die Sprache aus. Die Implementierung eines Anbieters IntelliSense Verweise verarbeitet und des Sprachcompilers aufruft, wenn eine intelligente Webseite, die nicht zwischengespeichert wird angefordert wird.  
  
 Sprachcompiler, die zum Kompilieren von Webseiten verwendet muss registriert werden, mit [!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]. Können Sie die [ \<Compiler >-Element](/dotnet/framework/configure-apps/file-schema/compiler/compiler-element) in einer Datei "Web.config" So registrieren den Compiler an, wie im folgenden Beispiel gezeigt:  
  
```  
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorlagen für die Websiteunterstützung](../../extensibility/internals/web-site-support-templates.md)  
 Listet die Vorlagen, die Sie verwenden können, um neue Websiteprojekte und zugehörige Elemente zu erstellen.  
  
 [Attribute der Websiteunterstützung](../../extensibility/internals/web-site-support-attributes.md)  
 Zeigt die Registrierungsattribute, die einem Websiteprojekt zu verbinden [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] und [!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)].  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Webprojekte](../../extensibility/internals/web-projects.md)  
 Bietet eine Übersicht über die zwei Arten von Webprojekten, Websiteprojekte und Webanwendungsprojekte.