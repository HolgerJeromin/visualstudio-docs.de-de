---
title: Debug-Engine | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines
ms.assetid: 148b1efc-ca07-4d8e-bdfc-c723a760c620
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 78bd5b732d7ea1714bb1c5627b570976e33a82c4
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39203887"
---
# <a name="debug-engine"></a>Debug-engine
Ein Debugmodul (DE) arbeitet mit den Interpreter oder das Betriebssystem wie z. B. Ausführung-Steuerelement, Haltepunkte und Ausdruck Auswertung Debugdienste bereit. Die DE ist verantwortlich für die Überwachung des Status eines gedebuggten Programms. Zu diesem Zweck führen Sie die DE unabhängig Methoden, in der unterstützten Runtime verfügbar sein sollen, ob von der CPU oder von APIs durch die Common Language Runtime bereitgestellt wird verwendet.  
  
 Beispielsweise stellt die common Language Runtime (CLR) Mechanismen zum Überwachen von eines laufenden Programms über die ICorDebugXXX-Schnittstellen bereit. Eine bereitgestellten Kompatibilitätsrichtlinie, die die CLR unterstützt werden die entsprechenden ICorDebugXXX Schnittstellen zum Nachverfolgen einer verwalteten Code zu debuggende Programm wird verwendet. Es kommuniziert dann alle Änderungen des Zustands für die Sitzung Debug-Manager (SDM), der solche Informationen an weiterleitet der [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
> [!NOTE]
>  Eine Debug-Engine ist eine bestimmte Laufzeit, also das System, in dem das Programm ausgeführt wird debuggten, ausgerichtet. Die CLR ist die Runtime für verwalteten Code, und die Win32-Laufzeit für systemeigene Windows-Anwendungen. Wenn die Sprache, die Sie erstellen eine dieser zwei Laufzeiten, Ziel kann [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] stellt bereits die erforderlichen Debug-Engines bereit. Sie implementieren müssen lediglich eine ausdrucksauswertung.  
  
## <a name="debug-engine-operation"></a>Debug-Engine-Vorgang  
 Die Überwachung Dienste werden über die DE-Schnittstellen implementiert und können dazu führen, dass das debugpaket für den Übergang zwischen verschiedenen Betriebsmodi. Weitere Informationen finden Sie unter [Betriebsmodi](../../extensibility/debugger/operational-modes.md). Es gibt in der Regel nur eine Implementierung von DE pro-Umgebung ausgeführt.  
  
> [!NOTE]
>  Es gibt separate DE-Implementierungen für Transact-SQL und [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)], VBScript und [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] eine einzelne DE freigeben.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ermöglicht das Debuggen debug-Engines führen Sie eine von zwei Arten: entweder im selben Prozess wie die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] shell oder in demselben Prozess wie das Zielprogramm gedebuggt wird. Die letztgenannte Form tritt gewöhnlich auf, wenn der gedebuggte Prozess tatsächlich ein Skript, die unter einem Interpreter ausgeführt wird. Die Debug-Engine benötigen sehr gute Kenntnisse über den Interpreter, um das Skript zu überwachen. In diesem Fall wird der Interpreter tatsächlich eine Laufzeit; Debug-Engines sind für eine spezifische Runtime-Implementierungen. Darüber hinaus kann die Implementierung von einem einzelnen DE über Prozess- und Computergrenzen hinweg (z. B. remote debugging) geteilt werden.  
  
 Die DE-macht die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Debugschnittstellen. Die gesamte Kommunikation wird über COM Ob die DE in-Process, Out-of-Process, oder auf einem anderen Computer geladen wird, wirkt es sich nicht Komponente Kommunikation.  
  
 Die DE funktioniert mit einer Expression Evaluator-Komponente die DE für diese bestimmte Laufzeit die Syntax von Ausdrücken zu aktivieren. Die DE funktioniert auch mit einer Symbol-Handler-Komponente auf den symbolischen Debuginformationen vom Sprachcompiler generiert werden. Weitere Informationen finden Sie unter [ausdrucksauswertung](../../extensibility/debugger/expression-evaluator.md) und [symbolanbieter](../../extensibility/debugger/symbol-provider.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugger-Komponenten](../../extensibility/debugger/debugger-components.md)   
 [Ausdrucksauswertung](../../extensibility/debugger/expression-evaluator.md)   
 [Symbolanbieter](../../extensibility/debugger/symbol-provider.md)