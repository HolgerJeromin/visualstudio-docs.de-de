---
title: Funktionsansicht – Samplingdaten | Microsoft-Dokumentation
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
- sampling profiling method,Functions View
- Functions view
ms.assetid: 029d5ebb-e551-46b0-b64e-2c553d9dbb8e
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3813c306c2240e7b9db0e8e3d5cbf5929cf0cf91
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509652"
---
# <a name="functions-view---sampling-data"></a>Funktionsansicht - Samplingdaten
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Funktionsansicht - Samplingdaten](https://docs.microsoft.com/visualstudio/profiling/functions-view-sampling-data).  
  
Die Funktionsberichtansicht für die Samplingprofilmethode listet die Funktionen auf, die während der Profilerstellung abgetastet wurden.  
  
> [!NOTE]
>  Verbesserte Sicherheitsfunktionen in Windows 8 und Windows Server 2012 erforderten tiefgreifende Änderungen bei der Datenerfassung des Visual Studio-Profilers auf diesen Plattformen. Außerdem benötigen Windows Store-Apps neue Erfassungsmethoden. Siehe [Profilerstellungstools für Windows 8- und Windows Server 2012-Anwendungen](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
|Spalte|Beschreibung|  
|------------|-----------------|  
|**Prozess-ID**|Die Prozess-ID (PID) der Profilerstellung.|  
|**Prozessname**|Der Prozessname.|  
|**Modulname**|Der Name des Moduls, das die Funktion enthält.|  
|**Modulpfad**|Der Pfad des Moduls, das die Funktion enthält.|  
|**Quelldatei**|Die Quelldatei, die die Definition der Funktion enthält.|  
|**Funktionsname**|Der vollqualifizierte Name der Funktion.|  
|**Funktionszeilennummer**|Die Zeilennummer des Anfangs dieser Funktion in der Quelldatei.|  
|**Funktionsadresse**|Die Adresse der Funktion.|  
|**Inklusive Samplings**|Die Gesamtzahl an Samplings, die während der Ausführung der Funktion erfasst wurden; d.h., die Anzahl der Samplings, die erfasst wurden, während sich die Funktion in der Aufrufliste befand. Darin sind Samplings enthalten, die während der Ausführung von Funktionen erfasst wurden, die von dieser Funktion aufgerufen wurden.|  
|**Inklusive Samplings in %**|Der Prozentsatz aller Samplings während der Profilerstellung, die inklusive Samplings dieser Funktion waren.|  
|**Exklusive Samplings**|Die Gesamtzahl an Samplings, die während der Ausführung von Code im Text der Funktion erfasst wurden, d.h., während sich die Funktion in der Aufrufliste befand. Samplings, die in von Funktionen, die von dieser Funktion aufgerufen wurden, erfasst wurden, sind nicht enthalten.|  
|**Exklusive Samplings %**|Der Prozentsatz aller Samplings während der Profilerstellung, die exklusive Samplings dieser Funktion waren.|  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Anpassen von Spalten in Berichtsansichten](../profiling/how-to-customize-report-view-columns.md)   
 [Funktionsansicht - Instrumentierung](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [Funktionsansicht - Sampling](../profiling/functions-view-dotnet-memory-sampling-data.md)   
 [Funktionsansicht](../profiling/functions-view-instrumentation-data.md)



