---
title: 'Vorgehensweise: Aktualisieren vorhandener Vorlagen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9c5d091e58904cae058c5a2a5ade1b8ceec4c738
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47512520"
---
# <a name="how-to-update-existing-templates"></a>Gewusst wie: Aktualisieren vorhandener Vorlagen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: Aktualisieren vorhandener Vorlagen](https://docs.microsoft.com/visualstudio/ide/how-to-update-existing-templates).  
  
Nachdem Sie eine Vorlage erstellt und die Dateien in einer ZIP-Datei komprimiert haben, möchten Sie die Vorlage vielleicht ändern. Dazu können Sie die Dateien in der Vorlage manuell ändern oder aber eine neue Vorlage aus einem Projekt exportieren, das auf der Vorlage basiert.  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>Verwenden des Assistenten "Vorlage exportieren" zum Aktualisieren einer vorhandenen Vorlage  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Stellt eine **Vorlage exportieren** -Assistenten, der zum Aktualisieren einer vorhandenen Vorlage verwendet werden kann.  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>So aktualisieren Sie eine vorhandene Vorlage mit "Vorlage exportieren"  
  
1.  Klicken Sie im Menü **Datei** auf **Neu** und dann auf **Neues Projekt**.  
  
2.  Wählen Sie die Vorlage, die Sie verwenden möchten, aktualisieren, geben einen Namen und Speicherort für das temporäre Projekt, und klicken Sie auf **OK**.  
  
3.  Ändern Sie das Projekt in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
4.  Auf der **Datei** Menü klicken Sie auf **Vorlage exportieren**, und Verwenden der **Vorlage exportieren** Assistenten, um eine neue Vorlage zu erstellen.  
  
5.  Nachdem die aktualisierte Vorlage in einer ZIP-Datei komprimiert wurde, löschen Sie die alte ZIP-Datei der Vorlage.  
  
## <a name="manually-updating-an-existing-template"></a>Manuelles Aktualisieren vorhandener Vorlagen  
 Sie können eine vorhandene Vorlage außerhalb von [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] aktualisieren, indem Sie die in der komprimierten ZIP-Datei enthaltenen Dateien ändern.  
  
#### <a name="to-manually-update-an-existing-template"></a>So aktualisieren Sie eine vorhandene Vorlage manuell  
  
1.  Suchen Sie die ZIP-Datei, die die Vorlage enthält. Standardmäßig befindet sich diese Datei im \My Documents\Visual Studio *Version*\My Exported Templates\\.  
  
2.  Extrahieren Sie die ZIP-Datei.  
  
3.  Ändern oder löschen Sie die aktuellen Vorlagendateien, oder fügen Sie der Vorlage neue Dateien hinzu.  
  
4.  Öffnen, ändern und speichern Sie die XML-Datei mit der Erweiterung .vstemplate, damit das geänderte Verhalten bzw. neue Dateien berücksichtigt werden. Weitere Informationen zum VSTEMPLATE-Schema finden Sie in der [Schemareferenz zu Visual Studio-Vorlagen](../extensibility/visual-studio-template-schema-reference.md). Weitere Informationen dazu, welche Elemente in den Quelldateien parametrisiert werden können, finden Sie unter [Vorlagenparameter](../ide/template-parameters.md)  
  
5.  Wählen Sie die Dateien in Ihrer Vorlage mit der rechten Maustaste, klicken Sie auf **senden an**, und klicken Sie dann auf **komprimierten (gezippten) Ordner**. Die ausgewählten Dateien werden in einer ZIP-Datei komprimiert.  
  
6.  Fügen Sie die neue ZIP-Datei in demselben Verzeichnis ein, in dem sich auch die alte ZIP-Datei befand.  
  
7.  Löschen Sie die extrahierten Vorlagendateien und die alte ZIP-Datei der Vorlage.  
  
8.  Starten Sie (als Administrator) eine Instanz der Developer-Eingabeaufforderung (im Startmenü unter **Visual Studio 2010 / Visual Studio-Tools/Developer-Eingabeaufforderung**).  
  
9. Führen Sie den folgenden Befehl aus: `devenv /installvstemplates`  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen von Vorlagen](../ide/customizing-project-and-item-templates.md)   
 [Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)   
 [Schemareferenz zu Visual Studio-Vorlagen](../extensibility/visual-studio-template-schema-reference.md)   
 [Vorlagenparameter](../ide/template-parameters.md)   
 [Gewusst wie: Erstellen von Starter Kits](../ide/how-to-create-starter-kits.md)



