---
title: 'Vorgehensweise: Suchen einer Meldung in der Meldungsansicht | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Search dialog box
- Messages view
- messages, searching for
ms.assetid: 732b7ccc-54ea-41db-823b-2b96e3e4083e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 984c3f0dc9b61059b53a7caf5a859d3413c99e62
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47516215"
---
# <a name="how-to-search-for-a-message-in-messages-view"></a>Gewusst wie: Suchen einer Meldung in der Meldungsansicht
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [wie: Suchen einer Meldung in der Meldungsansicht](https://docs.microsoft.com/visualstudio/debugger/how-to-search-for-a-message-in-messages-view).  
  
Sie können mithilfe der Handle, Typ oder Meldungs-ID als Suchkriterium für eine bestimmte Nachricht in der Ansicht "Nachrichten" suchen. Eine dieser – oder eine Kombination – werden gültige Suchkriterien. Die anfängliche Richtung für die Suche kann auch angegeben werden. Die Felder im Dialogfeld werden mit den Attributen der aktuell ausgewählten Nachricht vorab geladen.  
  
### <a name="to-search-for-a-message-in-messages-view"></a>Suchen Sie für eine Nachricht in der Meldungsansicht  
  
1.  Ordnen Sie die Fenster also, Spy++ und ein aktiver [Meldungsansicht](../debugger/messages-view.md) Fenster sichtbar sind.  
  
2.  Von der **Suche** Menü wählen **Nachricht suchen**.  
  
     Die [Nachricht Meldungssuche (Dialogfeld)](../debugger/message-search-dialog-box.md) wird geöffnet.  
  
3.  Ziehen Sie die **Suchtool** auf das gewünschte Fenster. Wie Sie das Tool, ziehen Sie die **Meldungssuche** Dialogfeld zeigt die Details für das ausgewählte Fenster.  
  
     – oder –  
  
     Wenn Sie das Handle des Fensters, deren Meldungen, die Sie untersuchen möchten verfügen, geben Sie ihn in das **behandeln** Textfeld.  
  
     – oder –  
  
     Wenn Sie wissen den Meldungstyp bzw. eine Meldungs-ID, die Sie möchten, wählen sie aus der **Typ** und **Nachricht** Dropdownmenüs, und deaktivieren Sie die **behandeln** Textfeld.  
  
4.  Deaktivieren Sie alle Felder, die für die Sie keine Werte angeben möchten.  
  
    > [!TIP]
    >  Um die Übersichtlichkeit des Bildschirms, wählen Sie die **Spy++ ausblenden** Option. Diese Option verbirgt die Spy++-Hauptfenster, sondern nur die **Fenster Suchen** Dialogfeld sichtbar ist, zusätzlich zu anderen Anwendungen. Spy++-Hauptfenster wird wiederhergestellt, wenn Sie auf **OK** oder **Abbrechen**, oder wenn Sie das Kontrollkästchen der **Spy++ ausblenden** Option.  
  
5.  Wählen Sie **einrichten** oder **unten** für die anfängliche Richtung für die Suche.  
  
6.  Klicken Sie auf **OK**.  
  
 Wenn eine entsprechende Nachricht gefunden wird, wird es in der Nachrichten an hervorgehoben. Finden Sie unter [Meldungsansicht](../debugger/messages-view.md).



