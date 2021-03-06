---
title: Installieren von Visual Studio SDK | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- visual-studio-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c730edb6-5099-4c16-85a8-08def09f1455
caps.latest.revision: 4
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1bbf029fb27e54b68fe6bef36d0c3f2f7329c45b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47515798"
---
# <a name="installing-the-visual-studio-sdk"></a>Installieren von Visual Studio SDK
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ab Visual Studio 2015, sind Sie nicht Visual Studio SDK aus dem Downloadcenter installieren. Er ist als optionales Feature in Visual Studio-Setup enthalten. Sie können das VS-SDK auch später installieren.  
  
## <a name="installing-the-visual-studio-sdk-as-part-of-a-visual-studio-installation"></a>Installieren von Visual Studio SDK als Teil einer Installation von Visual Studio  
 Wenn Sie das VS SDK in Visual Studio-Installation aufnehmen möchten, müssen Sie eine benutzerdefinierte Installation.  
  
> [!NOTE]
>  In der Installationsdatei, heißt das Visual Studio SDK **Visual Studio-Erweiterbarkeitstools**.  
  
1.  Starten Sie die Visual Studio 2015-Installation. Sie können eine beliebige Edition von Visual Studio mit Ausnahme von Express installieren.  
  
2.  Wählen Sie auf dem ersten Bildschirm **benutzerdefinierte**, nicht **Standard**. Klicken Sie auf **Weiter**.  
  
3.  Daraufhin sollte eine Strukturansicht der benutzerdefinierten Funktionen. Open **häufig verwendete Tools**. Daraufhin sollte **Visual Studio-Erweiterbarkeitstools** .  
  
     ![VSSDKInstall](../extensibility/media/vssdkinstall.png "VSSDKInstall")  
  
4.  Überprüfen Sie **Visual Studio-Erweiterbarkeitstools** , klicken Sie dann auf **Weiter** und die Installation fortzusetzen.  
  
## <a name="installing-the-visual-studio-sdk-after-installing-visual-studio"></a>Installation von Visual Studio SDK nach der Installation von Visual Studio  
 Wenn Sie Visual Studio SDK nach Abschluss der Installation von Visual Studio installieren möchten, sollten Sie wie folgt vorgehen:  
  
1.  Wechseln Sie zu **Systemsteuerung / Programme / Programme und Funktionen**, und suchen Sie nach **Visual Studio 2015**. Sie können das Visual Studio-SDK für eine beliebige Edition von Visual Studio 2015 außer Express installieren.  
  
2.  Mit der rechten Maustaste **Visual Studio 2015**, und klicken Sie dann auf **Änderung**. Die Seite "Installation" sollte angezeigt werden.  
  
3.  Das gleiche Verfahren wie in **Installation von Visual Studio SDK als Teil einer Visual Studio-Installation** oben.  
  
4.  Klicken Sie auf die **Visual Studio-Erweiterbarkeitstools** Link zur Installation von Visual Studio SDK.  
  
## <a name="installing-the-visual-studio-sdk-from-a-solution"></a>Installieren von Visual Studio SDK aus einer Projektmappe  
 Wenn Sie eine Lösung mit ein Erweiterbarkeitsprojekt öffnen, ohne zuerst das VS SDK installieren, werden Sie durch eine hervorgehobene Informationsleiste oben im Projektmappen-Explorer aufgefordert werden. Es sollte etwa wie folgt aussehen:  
  
 ![SolutionExplorerInstall](../extensibility/media/solutionexplorerinstall.png "SolutionExplorerInstall")  
  
## <a name="installing-the-visual-studio-sdk-from-the-command-line"></a>Installieren von Visual Studio SDK über die Befehlszeile  
 Sie können das VS SDK von der Befehlszeile aus installieren, mit der **' / installselectableitems '** zusammen mit Visual Studio-Installer. Weitere Informationen zum Verwenden von Befehlszeilenparametern mit dem Installer finden Sie unter [Installieren von Visual Studio 2015](../install/install-visual-studio-2015.md).  
  
 Hier ist das VS SDK automatisch mit dem Visual Studio 2015 Community-Installer zu installieren:  
  
```  
vs_community.exe /s /installSelectableItems VS_SDK_GROUPV1  
```  
  
 Beachten Sie, dass Sie Visual Studio-Installer verwenden müssen, der die installierte Version von Visual Studio entspricht. Wenn Sie Visual Studio Enterprise auf Ihrem Computer installiert haben, müssen Sie z. B. das Installationsprogramm für Visual Studio Enterprise (vs_enterprise.exe) ausführen.







