---
title: 'Vorgehensweise: Automatisches Erhöhen der ClickOnce-Veröffentlichungsversion | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], incrementing publish version automatically
- Publish Version property, incrementing
- ClickOnce deployment, incrementing publish version automatically
- publishing, ClickOnce
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: bf59ba569b7530accf4293954606923ee614d305
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509690"
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>Gewusst wie: Automatisches Erhöhen der ClickOnce-Veröffentlichungsversion
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: automatisch Erhöhen der ClickOnce-Veröffentlichungsversion](https://docs.microsoft.com/visualstudio/deployment/how-to-automatically-increment-the-clickonce-publish-version).  
  
Beim Veröffentlichen einer [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] -Anwendung, Ändern der `Publish Version` -Eigenschaft bewirkt, dass die Anwendung als Update veröffentlicht werden. Standardmäßig Visual Studio automatisch inkrementiert die `Revision` Anzahl von der `Publish Version` jedes Mal veröffentlichen Sie die Anwendung.  
  
 Sie können dieses Verhalten deaktivieren, auf die **veröffentlichen** auf der Seite die **Projekt-Designer**.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-disable-automatically-incrementing-the-publish-version"></a>So deaktivieren Sie automatisch Inkrementieren der Veröffentlichungsversion  
  
1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die **veröffentlichen** Registerkarte.  
  
3.  In der **Veröffentlichungsversion** deaktivieren Sie im Abschnitt der **Revisionsnummer automatisch mit jeder Veröffentlichung erhöhen** Kontrollkästchen.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Festlegen der ClickOnce-Veröffentlichungsversion](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [Veröffentlichen von ClickOnce-Anwendungen](../deployment/publishing-clickonce-applications.md)   
 [Gewusst wie: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



