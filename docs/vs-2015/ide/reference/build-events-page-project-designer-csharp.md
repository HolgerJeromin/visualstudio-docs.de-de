---
title: Seite „Buildereignisse“, Projekt-Designer (C#) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 86ada1d23490c4e154cbdb7ba17f81acbee1796a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47522862"
---
# <a name="build-events-page-project-designer-c"></a>Seite "Buildereignisse", Projekt-Designer (C#)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Seite "Buildereignisse", Projekt-Designer (c#)](https://docs.microsoft.com/visualstudio/ide/reference/build-events-page-project-designer-csharp).  
  
  
Verwenden Sie die Seite **Buildereignisse** des **Projekt-Designers**, um die Anweisungen der Buildkonfiguration anzugeben. Außerdem können Sie die Bedingungen angeben, unter denen sämtliche Postbuildereignisse ausgeführt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Angeben von Buildereignissen (C#)](../../ide/how-to-specify-build-events-csharp.md) und [Vorgehensweise: Festlegen von Buildereignissen (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Konfiguration**  
 Dieses Steuerelement kann auf dieser Seite nicht bearbeitet werden. Eine Beschreibung dieses Steuerelements finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Plattform**  
 Dieses Steuerelement kann auf dieser Seite nicht bearbeitet werden. Eine Beschreibung dieses Steuerelements finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Befehlszeile für Präbuildereignis**  
 Gibt sämtliche Befehle an, die vor dem Start des Buildvorgangs ausgeführt werden sollen. Klicken Sie auf **Präbuild bearbeiten...**, um das [Dialogfeld „Befehlszeile für Präbuildereignis“/„Befehlszeile für Postbuildereignis“](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md) anzuzeigen. In dieses Feld können Sie lange Befehle eingeben.  
  
> [!NOTE]
>  Präbuildereignisse werden nicht ausgeführt, wenn das Projekt auf dem neuesten Stand ist, und es wird kein Build gestartet.  
  
 **Befehlszeile für Postbuildereignis**  
 Gibt sämtliche Befehle an, die nach dem Abschluss des Buildvorgangs ausgeführt werden sollen. Klicken Sie auf **Postbuild bearbeiten...**, um das **Dialogfeld „Befehlszeile für Präbuildereignis“/„Befehlszeile für Postbuildereignis“** anzuzeigen. In dieses Feld können Sie lange Befehle eingeben.  
  
> [!NOTE]
>  Fügen Sie allen Postbuildbefehlen, die BAT-Dateien ausführen, eine `call`-Anweisung hinzu. Beispielsweise `call C:\MyFile.bat` oder `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Postbuildereignis ausführen**  
 Gibt die folgenden Bedingungen für das auszuführende Postbuildereignis an, wie in der folgenden Tabelle dargestellt.  
  
|Option|Ergebnis|  
|------------|------------|  
|**Immer**|Das Postbuildereignis wird ausgeführt, unabhängig davon, ob der Buildvorgang erfolgreich ist.|  
|**Bei erfolgreichem Erstellen**|Das Postbuildereignis wird ausgeführt, wenn der Buildvorgang erfolgreich ist. Deshalb wird das Ereignis sogar für ein aktuelles Projekt ausgeführt, solange der Buildvorgang erfolgreich ist.|  
|**Wenn der Build die Projektausgabe aktualisiert**|Das Postbuildereignis wird nur ausgeführt, wenn sich die Ausgabedatei des Compilers (.exe or .dll) von der vorherigen Ausgabedatei des Compilers unterscheidet. Deshalb wird kein Postbuildereignis ausgeführt, wenn das Projekt aktuell ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Festlegen von Buildereignissen (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Vorgehensweise: Angeben von Buildereignissen (C#)](../../ide/how-to-specify-build-events-csharp.md)   
 [Projekteigenschaftenverweise](../../ide/reference/project-properties-reference.md)   
 [Kompilieren und Erstellen](../../ide/compiling-and-building-in-visual-studio.md)



