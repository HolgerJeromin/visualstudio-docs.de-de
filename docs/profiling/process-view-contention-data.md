---
title: Prozessansicht - Konfliktdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Process view
ms.assetid: 8821d98c-0771-43b2-a38b-e9039a3abd75
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c8772bd6426632093bb23cc3094fe42ad433a8d
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257812"
---
# <a name="process-view---contention-data"></a>Prozessansicht: Konfliktdaten
Die Prozessansicht zeigt Konfliktdaten für die Prozesse und Threads, die während der Profilerstellung ausgeführt wurden.  
  
 Wenn Symbole verfügbar sind, werden Prozesse nach Namen aufgelistet. Wenn keine Symbole verfügbar sind, werden Prozesse nach zugewiesener Speicheradresse im Hexadezimalformat aufgelistet. Threads werden als untergeordnete Elemente des Prozesses aufgeführt, in dem sie erstellt wurden.  
  
 In der nachstehenden Tabelle werden die Werte der Spalten in der Prozessansicht erklärt.  
  
|Spalte|Beschreibung |  
|------------|-----------------|  
|**Anfangszeit**|Die Anzahl von Millisekunden oder Prozessorzyklen vom Anfang der Profilerstellung zum Anfang des Prozesses oder Threads.|  
|**Blockierte Zeit**|Die Gesamtzeit, für die die Ausführung von Funktionen des Prozesses oder Threads blockiert wurden.|  
|**Blockierte Zeit in %**|Der Prozentsatz der Lebensdauer des Prozesses oder Threads, in dem die Ausführung von Funktionen für den Prozess oder Thread blockiert wurden.|  
|**Konflikte**|Die Anzahl der Versuche, die Ausführung der Funktionen für den Prozess oder Thread zu blockieren.|  
|**Konflikte %**|Der Prozentsatz aller Konflikte in der Profilerstellungsausführung, die Konflikte des Prozesses oder Threads waren.|  
|**Endzeit**|Die Anzahl von Millisekunden oder Prozessorzyklen vom Anfang der Profilerstellung bis zum Anfang des Prozesses oder Threads.|  
|**ID**|Der vom System generierter Bezeichner für den Prozess oder Thread.|  
|**Lebensdauer**|Die Anzahl von Millisekunden oder Prozessorzyklen vom Anfang des Prozesses oder Threads bis ans Endes des Prozesses oder Threads oder dem Ende der Profilerstellung.|  
|**Typ**|Typ der Zeile, entweder vom Prozess oder Thread.<br /><br /> Nur in **VSReport**-Befehlszeilenberichten. Weitere Informationen finden Sie unter [VSPerfReport](../profiling/vsperfreport.md).|  
|**Name**|Der Name des Prozesses oder Threads.|  
|**Eindeutige ID**|Ein durch die Profilerstellung generierter Bezeichner, der für den Prozess oder Thread eindeutig ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Anpassen von Spalten in Berichtsansichten](../profiling/how-to-customize-report-view-columns.md)   
 [Prozessansicht](../profiling/process-view.md)