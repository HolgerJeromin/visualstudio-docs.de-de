---
title: 'Vorgehensweise: Angeben der offline- oder ClickOnce Onlineinstallationsmodus | Microsoft-Dokumentation'
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
- ClickOnce deployment, specifying install mode
- install mode
- online applications
- offline applications
- ClickOnce install mode
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 7f277966070e142ebc24d70acfcf4bf5502f419a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514090"
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>Gewusst wie: Angeben des Offline- oder Onlineinstallationsmodus von ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: Angeben der ClickOnce Offline oder Online-Modus installieren](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-the-clickonce-offline-or-online-install-mode).  
  
Die `Install Mode` für eine [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Anwendung bestimmt, ob die Anwendung offline oder online verfügbar sein wird. Bei der Auswahl **die Anwendung ist nur online verfügbar**, die Benutzer benötigen Zugriff auf die [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Veröffentlichungsort (einer Webseite oder eine Dateifreigabe) um die Anwendung auszuführen. Bei der Auswahl **der Anwendung ist auch offline verfügbar**, Einträge für die Anwendung hinzugefügt der **starten** Menü und die **Software** Dialogfeld; der Benutzer ist um die Anwendung auszuführen, wenn sie nicht verbunden werden können.  
  
 Die `Install Mode` kann festgelegt werden, auf die **veröffentlichen** auf der Seite die **Projekt-Designer**.  
  
 **Beachten Sie** der `Install Mode` kann auch mithilfe des Veröffentlichungs-Assistenten festgelegt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Veröffentlichen einer ClickOnce-Anwendung, die mit dem Webpublishing-Assistenten](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>Um eine ClickOnce-Anwendung nur online verfügbar machen  
  
1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die **veröffentlichen** Registerkarte.  
  
3.  In der **Installationsmodus und-Einstellungen** Bereich, klicken Sie auf die **die Anwendung ist nur online verfügbar** Optionsfeld aus.  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>Um eine ClickOnce-Anwendung online oder offline verfügbar machen  
  
1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**.  
  
2.  Klicken Sie auf die **veröffentlichen** Registerkarte.  
  
3.  In der **Installationsmodus und-Einstellungen** Bereich, klicken Sie auf die **der Anwendung ist auch offline verfügbar** Optionsfeld aus.  
  
     Bei der Installation die Anwendung Einträge hinzugefügt der **starten** Menü und **Software** in der Systemsteuerung.  
  
## <a name="see-also"></a>Siehe auch  
 [Veröffentlichen von ClickOnce-Anwendungen](../deployment/publishing-clickonce-applications.md)   
 [Vorgehensweise: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Auswählen einer Strategie für die ClickOnce-Bereitstellung](../deployment/choosing-a-clickonce-deployment-strategy.md)



