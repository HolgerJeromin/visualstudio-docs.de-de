---
title: MergeLocalizationDirectives-Aufgabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- localizing XAML [WPF MSBuild], moving comments and attributes to a separate file
- MergeLocalizationDirectives task [WPF MSBuild], parameters
- MergeLocalizationDirectives task [WPF MSBuild]
- moving localization comments and attributes to a separate file [WPF MSBuild]
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 78cf1405cf3a09d43aab21c53e64644db29af0de
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077700"
---
# <a name="mergelocalizationdirectives-task"></a>MergeLocalizationDirectives-Aufgabe
Der <xref:Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives>-Task führt die Lokalisierungsattribute und -kommentare aus einer oder mehreren [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]-Binärformatdateien für die gesamte Assembly in einer einzelnen Datei zusammen.  
  
## <a name="task-parameters"></a>Aufgabenparameter  
  
|Parameter|Beschreibung |  
|---------------|-----------------|  
|`GeneratedLocalizationFiles`|Erforderlicher **ITaskItem[]**-Parameter.<br /><br /> Gibt die Liste der Dateien mit Lokalisierungsrichtlinien für einzelne Dateien im [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]-Binärformat an.|  
|`OutputFile`|Erforderlicher **String**-Ausgabeparameter.<br /><br /> Gibt den Ausgabepfad der kompilierten Lokalisierungsrichtlinien-Assembly an.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können dem [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)]-Inhalt Lokalisierungsattribute und -kommentare hinzufügen. Mit [!INCLUDE[TLA#tla_wpf](../msbuild/includes/tlasharptla_wpf_md.md)]-Lokalisierungsunterstützung können Sie Lokalisierungsattribute und -kommentare entfernen und in einer von der generierten Assembly separaten *LOC*-Datei ablegen. Verwenden Sie hierzu das **LocalizationPropertyStorage**-Attribut. Weitere Informationen zu Lokalisierungsattributen und -kommentaren sowie **LocalizationPropertyStorage** finden Sie unter [Lokalisierungsattribute und -kommentare](/dotnet/framework/wpf/advanced/localization-attributes-and-comments).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Lokalisierungskommentare mehrerer [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]-Binärformatdateien in einer einzelnen *LOC*-Datei zusammengeführt.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MergeLocalizationDirectivesTask">  
    <MergeLocalizationDirectives   
      GeneratedLocalizationFiles="obj\debug\page1.loc;obj\debug\page2.loc;obj\debug\page3.loc"  
      OutputFile="obj\debug\WPFMSBuildSample.loc" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
[WPF-MSBuild-Referenz](../msbuild/wpf-msbuild-reference.md)  
[Referenz zu MSBuild-Tasks für WPF](../msbuild/wpf-msbuild-task-reference.md)  
[MSBuild-Referenz](../msbuild/msbuild-reference.md)  
[Referenz zu MSBuild-Tasks](../msbuild/msbuild-task-reference.md)  
[Erstellen einer WPF-Anwendung (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)  
