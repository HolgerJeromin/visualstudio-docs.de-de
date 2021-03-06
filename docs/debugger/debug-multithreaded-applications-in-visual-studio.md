---
title: Debuggen von Multithreadanwendungen in Visual Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.gputthreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], high-performance computing
- debugging [Visual Studio], multithreaded
- multithreaded debugging
- high-performance debugging
ms.assetid: 9d175bc2-1d95-4c47-9bc3-9755af968a9c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 80618257e61356285d9b8c9c2bcf2a7a2e11e831
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279544"
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>Debuggen von Multithreadanwendungen in Visual Studio
Ein Thread ist eine Folge von Anweisungen, für die das Betriebssystem Prozessorzeit reserviert. Jeder Prozess, der im Betriebssystem ausgeführt wird, umfasst mindestens einen Thread. Prozesse, die über mehr als einen Thread verfügen, werden als Multithreadprozesse bezeichnet.  
  
Auf Computern mit mehreren Prozessoren, Mehrkernprozessoren oder Hyperthreadingprozessen können mehrere Threads gleichzeitig ausgeführt werden. Die parallele Verarbeitung mehrerer Threads kann sich äußerst positiv auf die Programmleistung auswirken, andererseits aber auch das Debuggen erschweren, da in diesem Fall mehrere Threads verfolgt werden müssen.  
  
Außerdem werden durch das Multithreading neue potenzielle Fehlertypen eingeführt. Beispielsweise müssen zwei oder mehr Threads häufig auf dieselbe Ressource zugreifen, während jeweils nur ein Thread sicher auf die Ressource zugreifen kann. Um sicherzustellen, dass immer nur ein Thread auf die Ressource zugreifen kann, ist eine Form des gegenseitigen Ausschlusses erforderlich. Wenn gegenseitiger Ausschluss nicht ordnungsgemäß ausgeführt wird, können sie erstellen eine *Deadlock* Bedingung, der kein Thread ausgeführt werden kann. Deadlocks können beim Debuggen ein besonders schwerwiegendes Problem verursachen.

Visual Studio bietet verschiedene Tools für Verwendung beim Debuggen von Multithreadanwendungen.

- Für Threads, die wichtigsten Tools zum Debuggen von Threads sind die **Threads** , Threadmarker in Quellcodefenstern **parallele Stapel** Fenster **parallele Überwachung** Fenster und die **Debugspeicherort** Symbolleiste. Informationen zu den **Threads** Fenster und **Debugspeicherort** Symbolleiste finden Sie unter [Exemplarische Vorgehensweise: Debuggen mithilfe des Fensters Threads](../debugger/how-to-use-the-threads-window.md). Informationen zum Verwenden der **parallele Stapel** und **parallele Überwachung** Windows finden Sie unter [erste Schritte zum Debuggen einer Multithreadanwendung](../debugger/get-started-debugging-multithreaded-apps.md). Beide Themen zeigen, wie Threadmarker verwendet wird.
  
- Für Code, verwendet der [Task Parallel Library (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl) oder [Concurrency Runtime](/cpp/parallel/concrt/concurrency-runtime/), sind die wichtigsten Tools zum Debuggen der **parallele Stapel** Fenster, das **Parallele Überwachung** Fenster, und die **Aufgaben** Fenster (der **Aufgaben** Fenster unterstützt auch JavaScript). Informationen zum Einstieg finden Sie unter [Exemplarische Vorgehensweise: Debuggen einer Parallelanwendung](../debugger/walkthrough-debugging-a-parallel-application.md) und [Exemplarische Vorgehensweise: Debuggen einer C++ AMP-Anwendung](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application). 

- Zum Debuggen von Threads auf der GPU, die das primäre Tool ist das **GPU-Threads** Fenster. Finden Sie unter [Vorgehensweise: Verwenden von GPU-Threadfenster](../debugger/how-to-use-the-gpu-threads-window.md).  

- Für Prozesse, die wichtigsten Tools sind die **an den Prozess anhängen** im Dialogfeld die **Prozesse** Fenster, und die **Debugspeicherort** Symbolleiste.  
  
Visual Studio stellt auch leistungsstarke Halte- und Ablaufverfolgungspunkte bereit, die beim Debuggen von Multithreadanwendungen sehr hilfreich sein können. Sie können die haltepunktbedingungen und-Filter verwenden, um Haltepunkte auf einzelne Threads zu platzieren. Finden Sie unter [Verwenden von Haltepunkten](../debugger/using-breakpoints.md). 
  
Das Debuggen einer Multithreadanwendung mit einer Benutzeroberfläche kann besonders schwierig sein. In diesem Fall könnten Sie erwägen, die Anwendung auf einem zweiten Computer auszuführen und das Remotedebuggen zu verwenden. Weitere Informationen finden Sie unter [Remotedebuggen](../debugger/remote-debugging.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt
 [Erste Schritte zum Debuggen einer Multithreadanwendung](../debugger/get-started-debugging-multithreaded-apps.md).  
 Eine Tour Threaddebuggen, mit Schwerpunkt auf Funktionen in der **parallele Stapel** Fenster und **parallele Überwachung** Fenster.

 [Tools zum Debuggen von Threads und Prozessen](../debugger/debug-threads-and-processes.md)  
 Listet die Features der Tools zum Debuggen von Threads und Prozessen.  
  
 [Debuggen mehrerer Prozesse](../debugger/debug-multiple-processes.md)  
 Erläutert das Debuggen mehrerer Prozesse.

 [Exemplarische Vorgehensweise: Debuggen mithilfe des Fensters Threads](../debugger/how-to-use-the-threads-window.md).  
 Exemplarische Vorgehensweise, die zeigt, wie Sie mit der **Threads** Fenster und die **Debugspeicherort** Symbolleiste. 

 [Exemplarische Vorgehensweise: Debuggen einer parallelen Anwendung](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Exemplarische Vorgehensweise, die zeigt, wie Sie mit der **parallele Stapel** und **Aufgaben** Windows.  
  
 [Gewusst wie: Wechseln zu einem anderen Thread während des Debuggings](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
 Drei Möglichkeiten, um mit dem Debugkontext zu einem anderen Thread zu wechseln.  
  
 [Gewusst wie: Kennzeichnen von Threads und Aufheben der Kennzeichnung](../debugger/how-to-flag-and-unflag-threads.md)  
 Markieren oder Kennzeichnen von Threads, die beim Debuggen besondere Aufmerksamkeit erhalten sollen.    
  
 [Gewusst wie: Debuggen eines Hochleistungsclusters](../debugger/how-to-debug-on-a-high-performance-cluster.md)  
 Techniken zum Debuggen einer Anwendung, die auf einem Hochleistungscluster ausgeführt wird.  

 [Tipps zum Debuggen von Threads in nativem Code](../debugger/tips-for-debugging-threads-in-native-code.md)  
 Einfache Techniken, die beim Debuggen systemeigener Threads hilfreich sein können. 

 [Gewusst wie: Festlegen eines Threadnamens in nativem Code](../debugger/how-to-set-a-thread-name-in-native-code.md)  
 Benennen Sie Ihr Thread in der angezeigten der **Threads** Fenster.  
  
 [Gewusst wie: Festlegen eines Threadnamens in verwaltetem Code](../debugger/how-to-set-a-thread-name-in-managed-code.md)  
 Benennen Sie Ihr Thread in der angezeigten der **Threads** Fenster. 
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verwenden von Haltepunkten](../debugger/using-breakpoints.md)

 - Verwenden Sie breakpointbedingungen oder Filter aus, wenn Sie einen einzelnen Thread debuggen möchten.  
  
 - Ablaufverfolgungspunkte ermöglichen es Ihnen, die Ausführung des Programms ohne Unterbrechung zu verfolgen. Dies kann beim Untersuchen von Problemen wie Deadlocks hilfreich sein.  
  
 [Threading](/dotnet/standard/threading/index)  
 Threadingbegriffe in der [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]-Programmierung, einschließlich Beispielcode.  
  
 [Multithreading in Komponenten](https://msdn.microsoft.com/Library/2fc31e68-fb71-4544-b654-0ce720478779)  
 Erläutert die Verwendung des Multithreadings in [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]-Komponenten.  
  
 [Multithreadingunterstützung für älteren Code (Visual C++)](/cpp/parallel/multithreading-support-for-older-code-visual-cpp)  
 Threadingbegriffe und Beispielcode für C++-Programmierer, die MFC verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Threads und Prozessen](../debugger/debug-threads-and-processes.md)   
 [Remotedebuggen](../debugger/remote-debugging.md)