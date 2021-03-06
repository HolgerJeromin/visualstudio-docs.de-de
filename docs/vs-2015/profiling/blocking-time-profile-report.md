---
title: Blockierungszeit-Profilbericht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.report.blocking
helpviewer_keywords:
- Concurrency Visualizer, Blocking Time Profile Report
ms.assetid: 3bc45af0-3ba6-4fa3-a336-be8e9ae95107
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae0c4f34f0d3447f63afbf08e9d788304b2d353f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509583"
---
# <a name="blocking-time-profile-report"></a>Blockierungszeit-Profilbericht
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Zeit Profilbericht blockieren](https://docs.microsoft.com/visualstudio/profiling/blocking-time-profile-report).  
  
Die Profilberichte enthalten aggregierte Blockierungszeitdaten für spezifische Aufruflisten zu den einzelnen Blockierungskategorien (wie „E/A“ oder „Synchronisierung“). Der Bericht zur vorzeitigen Entfernung listet die Prozesse auf, die den aktuellen Prozess vorzeitig entfernt haben, und gibt die Anzahl der Instanzen für die vorzeitige Entfernung an. Um den Blockierungsprofilbericht zu erstellen, sammelt das Tool blockierende API-Aufrufe und stellt sie in einer Struktur von Aufruflisten zusammen. In diesen Berichten angezeigte Daten hängen vom aktuellen Zeitraum, von ausgeblendeten Threads und den beiden folgenden Filtern ab, die angewendet werden können:  
  
-   Wenn „Nur eigenen Code“ ausgewählt ist, werden nur Stapelrahmen mit Benutzercode sowie die Ebene direkt unter dem Benutzercode angezeigt.  
  
-   Wenn „Rauschunterdrückung“ festgelegt ist, werden sortierte Stapel mit einer geringeren als der angegebenen Frequenz übersprungen.  
  
 Erweitern Sie alle Aufrufstruktureinträge, um die Codezeile zu finden, auf die Blockierungszeit entfällt. Um die Quellzeile für einen Eintrag zu finden, wählen Sie in seinem Kontextmenü **Quelle anzeigen**. Um die für den Aufruf verwendete Codezeile zu suchen, wählen Sie im Kontextmenü **Aufrufsites anzeigen**. Wenn nur eine Aufrufsite vorhanden ist, stellt der Befehl die Verbindung zur markierten Codezeile für die Aufrufsite her. Wenn mehrere Aufrufsites verfügbar sind, öffnet der Befehl ein Dialogfeld, in dem Sie einen Eintrag auswählen können und dann die Schaltfläche **Gehe zu Quellcode** auswählen, um die markierte Aufrufsite zu suchen. Häufig ist es besonders hilfreich, Quellcode für die Aufrufsite anzuzeigen, auf die die meisten Instanzen, die meiste Zeit oder beides entfallen.  
  
## <a name="blocking-time-report-columns"></a>Spalten des Blockierungszeitberichts  
 Die folgende Tabelle zeigt die Spalten für die einzelnen Blockierungszeitberichte.  
  
|Spaltenname|Beschreibung|  
|-----------------|-----------------|  
|name|Der Name der Funktion für die einzelnen Ebenen der Aufrufliste.|  
|Instanzen|Die Anzahl der Instanzen des blockierenden Aufrufs für den sichtbaren Zeitraum.|  
|Inklusive Blockierungszeit|Die Gesamtblockierungszeit, die für alle Stapel angefallen ist, für die bis zu dieser Ebene der Aufruflistenstruktur ein Rollup ausgeführt wird. Die inklusive Zahl ist die Summe aus der exklusiven Blockierungszeit für diese Funktion und der exklusiven Blockierungszeit für alle untergeordneten Knoten.|  
|Exklusive Blockierungszeit|Die aufgewendete Gesamtblockierungszeit, während der sich diese Funktion auf der untersten Ebene der Aufrufliste befand. Ein eindeutiger Eintrag in der Aufrufliste, der eine hohe exklusive Blockierungszeit aufweist, kann eine interessante Funktion sein.|  
|API-/Warte-Kategorie|Wird nur für Funktionen auf der untersten Ebene der Aufrufliste angezeigt. Wenn die Signatur des blockierenden Aufrufs erkannt wird, wird der Name der blockierenden API angezeigt. Wird die Signatur nicht erkannt, werden vom Kernel gemeldete Informationen bereitgestellt.|  
|Details|Vollqualifizierter Name der Funktion. Dies umfasst die Zeilenanzahl, sofern verfügbar.|  
  
### <a name="synchronization"></a>Synchronisierung  
 Der Synchronisierungsbericht enthält die Aufrufe, die für bei der Synchronisierung blockierte Segmente verantwortlich sind, und die Gesamtblockierungszeit der einzelnen Aufruflisten. Weitere Informationen finden Sie unter [Synchronisierungszeit](../profiling/synchronization-time.md)  
  
### <a name="sleep"></a>Sleep  
 Der Standbybericht enthält die Aufrufe, die für Blockierungszeit verantwortlich sind, die im Standbymodus verbracht wurde, und die Gesamtblockierungszeit der einzelnen Aufruflisten. Weitere Informationen finden Sie unter [Standbyzeit](../profiling/sleep-time.md).  
  
### <a name="io"></a>E/A  
 Der E/A-Bericht enthält die Aufrufe, die für bei der E/A blockierte Segmente verantwortlich sind, und die Gesamtblockierungszeit der einzelnen Aufruflisten. Weitere Informationen finden Sie unter [E/A-Zeit (Threadansicht)](../profiling/i-o-time-threads-view.md).  
  
### <a name="memory-management"></a>Speicherverwaltung  
 Der Speicherverwaltungsbericht enthält die Aufrufe, die für bei Speicherverwaltungsvorgängen blockierte Segmente verantwortlich sind, und die Gesamtblockierungszeit der einzelnen Aufruflisten. Weitere Informationen finden Sie unter [Speicherverwaltungszeit](../profiling/memory-management-time.md).  
  
### <a name="preemption"></a>Vorzeitige Entfernung  
 Der Bericht zur vorzeitigen Entfernung listet die Prozesse auf, die den aktuellen Prozess vorzeitig entfernt haben, und gibt die Anzahl der Instanzen an.  Sie können jeden Prozess erweitern, um die konkreten Threads anzuzeigen, die Threads im aktuellen Prozess ersetzt haben, und um eine Aufschlüsselung der Instanzen der vorzeitigen Entfernung pro Thread anzuzeigen. Dieser Blockierungsbericht erfordert weniger Aktionen als die übrigen Berichte, da für die vorzeitige Entfernung Ihres Prozesses in der Regel das Betriebssystem und nicht ein Problem in Ihrem Code verantwortlich ist. Weitere Informationen finden Sie unter [Zeit für die vorzeitige Entfernung](../profiling/preemption-time.md).  
  
### <a name="ui-processing"></a>Benutzeroberflächenverarbeitung  
 Der E/A-Verarbeitungsbericht enthält die Aufrufe, die für bei der Benutzeroberflächenverwaltung blockierte Segmente verantwortlich sind, und die Gesamtblockierungszeit der einzelnen Aufruflisten. Weitere Informationen finden Sie unter [Benutzeroberflächenverarbeitungszeit](../profiling/ui-processing-time.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Threads View (Threadansicht)](../profiling/threads-view-parallel-performance.md)



