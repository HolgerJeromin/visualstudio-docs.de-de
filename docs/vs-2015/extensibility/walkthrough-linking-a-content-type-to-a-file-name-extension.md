---
title: 'Exemplarische Vorgehensweise: Verknüpfen eines Inhaltstyps mit einer Dateinamenerweiterung | Microsoft-Dokumentation'
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
- editors [Visual Studio SDK], new - link content type to file name extension
ms.assetid: 21ee64ce-9afe-4b08-94a0-8389cc4dc67c
caps.latest.revision: 25
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1742da19e2d99cbb22d930b7146b1f9859e19cef
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524735"
---
# <a name="walkthrough-linking-a-content-type-to-a-file-name-extension"></a>Exemplarische Vorgehensweise: Verknüpfen eines Inhaltstyps mit einer Dateinamenerweiterung
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Exemplarische Vorgehensweise: Verknüpfen eines Inhaltstyps mit einer Dateinamenerweiterung](https://docs.microsoft.com/visualstudio/extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension).  
  
Sie können einen eigenen Inhaltstyp definieren, und verknüpfen eine Dateinamenerweiterung, mithilfe von Erweiterungen des Editors Managed Extensibility Framework (MEF). In einigen Fällen wurde die Erweiterung bereits von einem Sprachdienst definiert. dennoch müssen für die Verwendung mit MEF Sie weiterhin diese an einen Inhaltstyp verknüpfen.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Ab Visual Studio 2015, sind Sie nicht Visual Studio SDK aus dem Downloadcenter installieren. Er ist als optionales Feature in Visual Studio-Setup enthalten. Sie können das VS-SDK auch später installieren. Weitere Informationen finden Sie unter [Installieren von Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Erstellen eines MEF-Projekts  
  
1.  Erstellen Sie ein C#-VSIX-Projekt. (In der **neues Projekt** wählen Sie im Dialogfeld **Visual c# / Erweiterbarkeit**, klicken Sie dann **VSIX-Projekt**.) Nennen Sie die Projektmappe `ContentTypeTest`.  
  
2.  In der **"Source.Extension.vsixmanifest"** -Datei, wechseln Sie zu der **Assets** , und legen die **Typ** Feld **Microsoft.VisualStudio.MefComponent**, **Quelle** Feld **ein Projekt in der aktuellen Projektmappe**, und die **Projekt** Feld auf den Namen des Projekts.  
  
## <a name="defining-the-content-type"></a>Definieren den Inhaltstyp  
  
1.  Fügen Sie eine Klassendatei hinzu, und nennen Sie sie `FileAndContentTypes`.  
  
2.  Fügen Sie Verweise auf die folgenden Assemblys hinzu:  
  
    1.  System.ComponentModel.Composition  
  
    2.  Microsoft.VisualStudio.Text.Logic  
  
    3.  Microsoft.VisualStudio.CoreUtility  
  
3.  Fügen Sie die folgenden `using` Anweisungen.  
  
    ```csharp  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Classification;  
    using Microsoft.VisualStudio.Utilities;  
  
    ```  
  
4.  Deklarieren Sie eine statische Klasse, die die Definitionen enthält.  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {. . .}  
    ```  
  
5.  In dieser Klasse Exportieren einer <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> mit dem Namen "hid", und deklarieren Sie die Basisdefinition "Text" sein.  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {  
        [Export]  
        [Name("hid")]  
        [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
    }  
    ```  
  
## <a name="linking-a-file-name-extension-to-a-content-type"></a>Verknüpfen eine Dateinamenerweiterung mit einem Inhaltstyp  
  
-   Um eine Dateinamenerweiterung dieser Inhaltstyp zuzuordnen, Exportieren einer <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> , die über die Erweiterung "HID-Dateien" und der Inhaltstyp "hid".  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {  
         [Export]  
         [Name("hid")]  
         [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
  
         [Export]  
         [FileExtension(".hid")]  
         [ContentType("hid")]  
        internal static FileExtensionToContentTypeDefinition hiddenFileExtensionDefinition;  
    }  
    ```  
  
## <a name="adding-the-content-type-to-an-editor-export"></a>Hinzufügen des Inhaltstyps mit einem Export-Editor  
  
1.  Erstellen einer Editor-Erweiterungs. Sie können z. B. die Rand Symbol-Erweiterung, die in beschriebenen [Exemplarische Vorgehensweise: Erstellen einer Randglyphe](../extensibility/walkthrough-creating-a-margin-glyph.md).  
  
2.  Fügen Sie der Klasse, die Sie in diesem Verfahren definiert.  
  
3.  Beim Exportieren der Erweiterungsklasse Hinzufügen einer <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> vom Typ "hid" zuzuweisen.  
  
    ```csharp  
    [Export]  
    [ContentType("hid")]  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterungspunkte für den Sprachdienst und den Editor](../extensibility/language-service-and-editor-extension-points.md)

