---
title: 'Vorgehensweise: Angeben eines anderen Speicherorts für Bereitstellungsaktualisierungen | Microsoft-Dokumentation'
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
- ClickOnce deployment, updates
- deployment update, alternative locations
ms.assetid: 7faacd35-2638-492d-80f6-6b57e5f820de
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: a0db7eddc38a2b2ab3581ba2b1ff04c90e2adb77
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524717"
---
# <a name="how-to-specify-an-alternate-location-for-deployment-updates"></a>Gewusst wie: Angeben eines anderen Speicherorts für Bereitstellungsaktualisierungen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: Angeben eines anderen Speicherorts für Bereitstellungsaktualisierungen](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-an-alternate-location-for-deployment-updates).  
  
Sie installieren können Ihre [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Anwendung zunächst von einer CD oder eine Dateifreigabe, aber die Anwendung muss überprüfen, regelmäßig nach Updates suchen im Web. Sie können einen alternativen Speicherort für Updates im Bereitstellungsmanifest angeben, damit Ihre Anwendung selbst aus dem Web nach der Erstinstallation kann aktualisiert werden.  
  
> [!NOTE]
>  Ihre Anwendung muss konfiguriert werden, zum Installieren von lokal aus, um dieses Feature zu verwenden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Darüber hinaus, wenn es sich bei der Installation einer [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aus dem Netzwerk, wird ein alternativer Speicherort festgelegt, wird Anwendung [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] diesen Speicherort für die Erstinstallation und alle nachfolgenden Updates verwendet. Wenn Sie Ihre Anwendung lokal (z. B. von einer CD) installieren, die erste Installation erfolgt, verwenden die ursprünglichen Medien und alle nachfolgenden Updates am alternativen Speicherort verwenden.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageuiexe-windows-forms-based-utility"></a>Angeben eines alternativen Speicherorts für Updates mit MageUI.exe (Windows Forms-basierten-Hilfsprogramm)  
  
1.  Öffnen Sie einen .NET Framework-Eingabeaufforderung, und geben:  
  
     **MageUI.exe**  
  
2.  Auf der **Datei** Menü wählen **öffnen** zu Ihrer Anwendung das Bereitstellungsmanifest öffnen.  
  
3.  Wählen Sie die **Bereitstellungsoptionen** Registerkarte.  
  
4.  In das Textfeld mit dem Namen **starten Speicherort**, geben Sie die URL in das Verzeichnis, das das Bereitstellungsmanifest für Anwendungsupdates enthält.  
  
5.  Speichern Sie das Bereitstellungsmanifest.  
  
### <a name="specifying-an-alternate-location-for-updates-by-using-mageexe"></a>Angeben eines alternativen Speicherorts für Updates mit Mage.exe  
  
1.  Öffnen Sie eine .NET Framework-Eingabeaufforderung.  
  
2.  Legen Sie den Speicherort für die Aktualisierung mithilfe des folgenden Befehls. In diesem Beispiel **HelloWorld.exe.application** ist der Pfad zu Ihrem [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Anwendungsmanifest, das die Erweiterung .application immer aufweist, und **http://adatum.com/Update/Path** ist die URL, [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Anwendungsupdates überprüft.  
  
     **Mage-HelloWorld.exe.application - ProviderUrl aktualisieren http://adatum.com/Update/Path**  
  
3.  Speichern Sie die Datei.  
  
    > [!NOTE]
    >  Nun müssen Sie die Datei mit Mage.exe erneut signieren. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie die Anwendung aus einer offline Medium wie einer CD installieren, und der Computer online ist, [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] überprüft zuerst die URL, die gemäß der `<deploymentProvider>` -Tag im Bereitstellungsmanifest, um zu bestimmen, ob der Speicherort für die Aktualisierung auf eine neuere Version der enthält die die Anwendung. Wenn dies der Fall, [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] installiert die Anwendung direkt von dort statt aus dem ursprünglichen Installationsverzeichnis, und die common Language Runtime (CLR) bestimmt die Vertrauensebene der Anwendung mithilfe `<deploymentProvider>`. Wenn der Computer offline ist oder `<deploymentProvider>` ist nicht erreichbar, [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Installationen von CD, und die CLR gewährt vertrauen, die basierend auf den Installationspunkt; bei einer Installation von CD bedeutet dies Ihre Anwendung erhält volle Vertrauenswürdigkeit. Alle nachfolgenden Updates, die dieser Vertrauensebene erben.  
  
 Alle [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Anwendungen, die `<deploymentProvider>` sollten die Berechtigungen, die erforderlich sind, im Anwendungsmanifest, explizit deklarieren, damit die Anwendung keine unterschiedliches Maß an Vertrauenswürdigkeit auf verschiedenen Computern erhält.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [ClickOnce-Bereitstellungsmanifest](../deployment/clickonce-deployment-manifest.md)   
 [Sichern von ClickOnce-Anwendungen](../deployment/securing-clickonce-applications.md)   
 [Auswählen einer Strategie für die ClickOnce-Aktualisierung](../deployment/choosing-a-clickonce-update-strategy.md)



