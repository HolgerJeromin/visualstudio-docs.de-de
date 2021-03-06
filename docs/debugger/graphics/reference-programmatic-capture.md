---
title: Verweis (programmgesteuerte Aufzeichnung) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd6ea361d0cec07e3f1fe1a3d5b6771ec7fcb5d6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474387"
---
# <a name="reference-programmatic-capture"></a>Verweis (Programmgesteuerte Aufzeichnung)
Die Grafikdiagnose unterstützt die programmgesteuerte Kontrolle über ihre Erfassungsfunktionen durch die programmgesteuerte Erfassungs-API. Sie können diese API verwenden, um Meldungen an das Grafikdiagnose-HUD (Head-Up-Display) ein- und auszuschalten und hinzuzufügen, Grafikprotokolldateien zu initialisieren und zu erstellen und Grafikinformationen zu erfassen.  
  
## <a name="programmatic-capture-apis"></a>Programmgesteuerte Erfassungs-APIs  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[VsgDbg-Klasse](vsgdbg-class.md)|Stellt die Schnittstelle dar, durch die die In-App-Komponente der Grafikdiagnose programmgesteuert kontrolliert wird.|  
  
### <a name="preprocessor-symbols"></a>Präprozessorsymbole  
  
|name|Beschreibung|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)|Definiert durch das Vorhandensein, ob die Grafikprotokolldatei im Verzeichnis der temporären Dateien des Benutzers gespeichert wird.|  
|[VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)|Definiert den Standarddateinamen der Grafikprotokolldatei.|  
|[VSG_NODEFAULT_INSTANCE](vsg-nodefault-instance.md)|Definiert durch das Vorhandensein, ob eine Standardinstanz der `VsgDbg`-Klasse bereitgestellt wird.|  
  
## <a name="related-articles"></a>Verwandte Artikel  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Capturing Graphics Information](capturing-graphics-information.md)|Zeigt wie Grafikinformationen aus Ihrer DirectX-basierten App erfasst werden können, sodass Sie [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]-Grafikdiagnosetools verwenden können, um Renderingprobleme zu diagnostizieren.|  
|[Übersicht](overview-of-visual-studio-graphics-diagnostics.md)|Zeigt, wie die Grafikdiagnose helfen kann, Renderingfehler in DirectX-Spielen und -Apps zu debuggen.|