---
title: 'Vorgehensweise: Debuggen einer .NET Framework-Quelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, .NET Framework source
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 250c2bd633a4f6c6b0580b23d0fbf1bb25094247
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509504"
---
# <a name="how-to-debug-net-framework-source"></a>Gewusst wie: Debuggen einer .NET Framework-Quelle
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: Debuggen von .NET Framework-Quellcodes](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-dotnet-framework-source).  
  
Die neueste Version der [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] bietet neue Funktionen für [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Debuggen. So debuggen Sie [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Quelle, benötigen Sie Zugriff auf Debugsymbole für den Code. Sie müssen auch-Quellcodes aktivieren [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Quelle.  
  
 Sie können [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] schrittweise ausführen und das Symbol im Download der **Optionen** im Dialogfeld. Wenn Sie das Herunterladen von Symbolen aktivieren, können Sie angeben, ob Symbole sofort heruntergeladen werden sollen, oder Sie können die Option für das spätere Herunterladen aktivieren. Wenn Sie die Symbole nicht sofort herunterladen, werden die Symbole heruntergeladen, wenn Sie das nächste Mal einen Debugvorgang Ihrer Anwendung starten. Auch möglich, einen manuellen Download über die **Module** Fenster oder der **Aufrufliste** Fenster.  
  
### <a name="to-enable-net-framework-source-debugging"></a>So aktivieren Sie das Debuggen des .NET Framework-Quellcodes  
  
1.  Auf der **Tools** Menü klicken Sie auf **Option**s.  
  
2.  In der **Optionen** Dialogfeld klicken Sie auf die **Debuggen** Kategorie.  
  
3.  In der **allgemeine** legen **.NET Framework aktivieren** -Quellcodes.  
  
    1.  Wenn Sie Nur Mein Code aktiviert haben, wird Ihnen in einem Warndialogfeld mitgeteilt, dass Nur mein Code jetzt deaktiviert wird. Klicken Sie auf **OK**.  
  
    2.  Wenn Sie keinen Speicherort für den Symbolcache festgelegt haben, teilt Ihnen ein anderes Warndialogfeld mit, dass jetzt ein Standardspeicherort für den Symbolcache festgelegt wird. Klicken Sie auf **OK**.  
  
4.  Unter den **Debuggen** (Kategorie), klicken Sie auf **Symbole**.  
  
5.  Gehen Sie wie folgt vor, wenn Sie den Speicherort des Symbolverzeichnisses ändern möchten:  
  
    1.  Öffnen der **Debuggen** Knoten in das Feld auf der linken Seite.  
  
    2.  Unter den **Debuggen** Knoten, klicken Sie auf **Symbole**.  
  
    3.  Bearbeiten Sie den Speicherort in **Symbole vom Symbolserver in diesem Verzeichnis zwischenspeichern** oder klicken Sie auf **Durchsuchen** , einen Standort auszuwählen.  
  
6.  Wenn Sie Symbole sofort herunterladen möchten, klicken Sie auf **Symbole laden von oben angegebenen Speicherorten**.  
  
     Diese Schaltfläche ist im Entwurfsmodus nicht verfügbar.  
  
     Wenn Sie die Symbole nicht sofort herunterladen, werden die Symbole automatisch heruntergeladen, wenn Sie das nächste Mal einen Debugvorgang Ihres Programms starten.  
  
7.  Klicken Sie auf **OK**, um das Dialogfeld **Optionen** zu schließen.  
  
### <a name="to-load-framework-symbols-using-the-modules-window"></a>So laden Sie Frameworksymbole mit dem Fenster "Module"  
  
1.  In der **Module** Fenster mit der rechten Maustaste ein Modul, die für den keine Symbole geladen sind. Sie können feststellen, ob Symbole geladen sind oder nicht anhand der **Symbolstatus** Spalte.  
  
2.  Zeigen Sie auf **Symbole laden aus** , und klicken Sie auf **Microsoft-Symbolserver** um Symbole von den öffentlichen Symbolserver Microsoft herunterzuladen oder **Symbolpfad** zum Laden aus einem Verzeichnis in dem Sie zuvor Symbole gespeichert haben.  
  
### <a name="to-load-framework-symbols-using-the-call-stack-window"></a>So laden Sie Frameworksymbole mit dem Fenster "Aufrufliste"  
  
1.  In der **Aufrufliste** Fenster mit der rechten Maustaste einen Rahmen, die für den keine Symbole geladen sind. Der Rahmen wird abgeblendet.  
  
2.  Zeigen Sie auf **Symbole laden aus** , und klicken Sie auf **Microsoft-Symbolserver** oder **Symbolpfad**.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von verwaltetem Code](../debugger/debugging-managed-code.md)   
 [Angeben von Symbol(PDB)- und Quelldateien](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)



