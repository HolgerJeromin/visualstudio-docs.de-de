---
title: 'Vorgehensweise: Erstellen eines lokalisierten Bootstrapperpakets | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- localized bootstrapper packages
- dependencies, creating localized bootstrapper packages
- prerequisites, creating localized bootstrapper packages
ms.assetid: 66a1bc7e-6540-4164-963d-557196a69d8a
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: cf92009cc7eadde4594bc8edb70f553b09b48010
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514322"
---
# <a name="how-to-create-a-localized-bootstrapper-package"></a>Gewusst wie: Erstellen eines lokalisierten Bootstrapperpakets
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: Erstellen eines lokalisierten Bootstrapperpakets](https://docs.microsoft.com/visualstudio/deployment/how-to-create-a-localized-bootstrapper-package).  
  
Nachdem Sie ein Bootstrapperpaket erstellt haben, können Sie lokalisierte Versionen des Bootstrapperpakets erstellen, indem Sie mindestens zwei Dateien für jedes Gebietsschema erstellen: eine Datei mit Softwarelizenzbedingungen (z. B. eula.rtf) und ein Paketmanifest (package.xml).  
  
 Visual Studio 2010 umfasst standardmäßig nur lokalisierte Bootstrapperpakete für .NET Framework 4, .NET Framework 4 Client Profile, F# Runtime 2.0 und F# Runtime 4.0. Mit den folgenden drei Schritten können Sie lokalisierte Pakete für andere Bootstrapper erstellen.  
  
1.  Erstellen Sie einen Ordner mit dem Namen des Gebietsschemas unter \Programme\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\*Bootstrapperpaketname*.  
  
2.  Erstellen Sie eine Datei, die die Softwarelizenzbedingungen für das Bootstrapperpaket enthält, und legen Sie diese in dem neuen Ordner ab.  
  
3.  Erstellen Sie ein Paketmanifest mit dem Namen "package.xml", aktualisieren Sie die Zeichenfolgen und die Kultur, und legen Sie die Datei in dem neuen Ordner ab. Wenn Sie bereits ein Bootstrapperpaket von Visual Studio in der Zielsprache erstellt haben, können Sie die Visual Studio-Datei "package.xml" kopieren und in diesem Schritt ändern.  
  
> [!NOTE]
>  Wenn Sie ein Setup-Projekt zum Bereitstellen von Anwendungen verwenden, können Sie Ihre Anwendung lokalisieren, indem Sie ändern die **Lokalisierung** Eigenschaft.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-localized-bootstrapper-package"></a>So erstellen Sie ein lokalisiertes Bootstrapperpaket  
  
1.  Erstellen Sie einen Ordner mit dem Namen des Gebietsschemas.  
  
     Erstellen Sie auf 32-Bit-Computern den Ordner im \Programme\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\*Bootstrapperpaketname*\ Ordner.  
  
     Erstellen Sie den Ordner auf 64-Bit-Computern in der \Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\*Bootstrapperpaketname*\ Ordner.  
  
     In der folgenden Tabelle sind die Ordnernamen dargestellt, die Sie für die Übereinstimmung mit einem Gebietsschema verwenden können.  
  
    |Gebietsschema|Ordnername|  
    |------------|-----------------|  
    |Chinesisch (vereinfacht)|zh-Hans|  
    |Chinesisch (traditionell)|zh-Hant|  
    |Tschechisch|cs|  
    |Deutsch|de|  
    |Englisch|en|  
    |Spanisch|es|  
    |Französisch|fr|  
    |Italienisch|it|  
    |Koreanisch|ko|  
    |Japanisch|ja|  
    |Polnisch|pl|  
    |Portugiesisch (Brasilien)|pt-BR|  
    |Russisch|ru|  
    |Türkisch|tr|  
  
2.  Erstellen Sie eine Datei, die die Softwarelizenzbedingungen für das Bootstrapperpaket enthält, und legen Sie diese in dem neuen Ordner ab.  
  
3.  Erstellen Sie ein Paketmanifest mit dem Namen "package.xml", und legen Sie die Datei in dem neuen Ordner ab. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Paketmanifests](../deployment/how-to-create-a-package-manifest.md).  
  
4.  Aktualisieren Sie den Abschnitt `<Strings>` des Paketmanifests so, dass die Zeichenfolgen die korrekte Sprache für das Gebietsschema aufweisen.  
  
5.  Ändern Sie den Wert `<String Name="Culture">` so, dass er mit dem Ordnernamen übereinstimmt.  
  
6.  Speichern Sie die Datei "package.xml".  
  
### <a name="to-create-a-bootstrapper-package-for-net-framework-35-service-pack-1-localized-in-french"></a>So erstellen Sie ein Bootstrapperpaket für .NET Framework 3.5 Service Pack 1 lokalisiert in Französisch  
  
1.  Erstellen Sie einen Ordner mit dem Namen "fr". Der Ordnername muss mit dem Gebietsschemanamen übereinstimmen.  
  
     Erstellen Sie auf 32-Bit-Computern den Ordner im Ordner \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\.  
  
     Erstellen Sie auf 64-Bit-Computern den Ordner im Ordner \Program Files (86)\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\.  
  
2.  Legen Sie eine lokalisierte Version der Softwarelizenzbedingungen im Ordner "fr" ab.  
  
3.  Kopieren Sie die Datei "\Program Files (x86)\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\en\package.xml" in den Ordner "fr", und öffnen Sie die Datei im XML-Designer.  
  
4.  Aktualisieren Sie den Abschnitt `<Strings>` des Paketmanifests so, dass die Fehlerzeichenfolgen auf Französisch sind.  
  
5.  Ändern Sie den Wert `<String Name="Culture">` in "fr".  
  
6.  Speichern Sie die Datei "package.xml".  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Bootstrapperpaketen](../deployment/creating-bootstrapper-packages.md)   
 [Vorbedingungen für die Anwendungsbereitstellung](../deployment/application-deployment-prerequisites.md)   
 [Gewusst wie: Erstellen eines Paketmanifests](../deployment/how-to-create-a-package-manifest.md)



