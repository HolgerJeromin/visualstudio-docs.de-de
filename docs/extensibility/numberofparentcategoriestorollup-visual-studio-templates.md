---
title: NumberOfParentCategoriesToRollUp (Visual Studio-Vorlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#NumberOfParentCategoriesToRollUp
helpviewer_keywords:
- NumberOfParentCategoriesToRollUp element [Visual Studio Templates]
- <NumberOfParentCategoriesToRollUp> element [Visual Studio Templates]
ms.assetid: 6f9d36f5-ae23-4a92-8132-b11799e2c21a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e6c3eae15aaa4aa7b81148915fc2c59fee723230
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639512"
---
# <a name="numberofparentcategoriestorollup-visual-studio-templates"></a>NumberOfParentCategoriesToRollUp (Visual Studio-Vorlagen)
Gibt die Anzahl der übergeordneten Kategorien, die die Vorlage in anzeigen, wird die **neues Projekt** Dialogfeld.  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<NumberOfParentCategoriesToRollUp >  
  
## <a name="syntax"></a>Syntax  
  
```  
<NumberOfParentCategoriesToRollUp>  
    1  
</NumberOfParentCategoriesToRollUp>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Kategorisiert die Vorlage und definiert, wie diese in den Dialogfeldern **Neues Projekt** oder **Neues Element hinzufügen** angezeigt wird.|  
  
## <a name="text-value"></a>Textwert  
 Ein `integer` Wert ist erforderlich.  
  
 Dieser Wert gibt die Anzahl der übergeordneten Kategorien, die die Vorlage in anzeigen, wird die **neues Projekt** Dialogfeld.  
  
## <a name="remarks"></a>Hinweise  
 `NumberOfParentCategoriesToRollUp` ist ein optionales Element.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, die Metadaten für eine [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Windows-Anwendung. Wenn eine Vorlage mit diesen Metadaten zwei Ordnerebenen unterhalb der obersten Ebene platziert wird [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Knoten, die Vorlage angezeigt, in den obersten Knoten in der **neues Projekt** Dialogfeld. Wenn die `NumberOfParentCategoriesToRollUp` ist nicht festgelegt ist, wird die Vorlage erscheint nur in den Knoten in der sie physisch befindet.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <NumberOfParentCategoriesToRollUp>2</NumberOfParentCategoriesToRollUp>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schemareferenz zu Visual Studio-Vorlage](../extensibility/visual-studio-template-schema-reference.md)   
 [Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)