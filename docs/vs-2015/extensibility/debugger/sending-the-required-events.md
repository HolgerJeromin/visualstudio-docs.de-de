---
title: Senden die erforderlichen Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], required events
ms.assetid: 08319157-43fb-44a9-9a63-50b919fe1377
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d1a3803b12c2941f9e76d1bb97d5885940197192
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523159"
---
# <a name="sending-the-required-events"></a>Senden der erforderlichen Ereignisse
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Senden der erforderlichen Ereignisse](https://docs.microsoft.com/visualstudio/extensibility/debugger/sending-the-required-events).  
  
Verwenden Sie dieses Verfahren für das Senden der erforderlichen Ereignisse an.  
  
## <a name="process-for-sending-required-events"></a>Prozess beim Senden der erforderlichen Ereignisse  
 Die folgenden Ereignisse sind erforderlich, in der Reihenfolge, erstellen eine Debug-engine (DE), und fügen Sie diesen mit einem Programm:  
  
1.  Senden einer [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) Ereignisobjekt für die Sitzung Debug-Manager (SDM), wenn die DE für das Debuggen von einem oder mehreren Programmen in einem Prozess initialisiert wird.  
  
2.  Wenn das Programm zu debuggende angefügt ist, Senden einer [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) Event-Objekt, das SDM. Dieses Ereignis kann es sich um eine Beenden-Ereignis, abhängig von Ihrem Entwurf Engine sein.  
  
3.  Wenn das Programm an angefügt ist, wenn der Prozess gestartet wird, senden Sie eine [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) Event-Objekt, das SDM, um die IDE den neuen Thread zu benachrichtigen. Dieses Ereignis kann es sich um eine Beenden-Ereignis, abhängig von Ihrem Entwurf Engine sein.  
  
4.  Senden einer [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) Event-Objekt, das SDM, wenn das derzeit debuggte Programm fertig geladen oder beim Anfügen an das Programm abgeschlossen ist. Dieses Ereignis muss einen Stopping-Ereignis.  
  
5.  Wenn die zu debuggende Anwendung gestartet wird, senden Sie eine [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) Event-Objekt, das SDM, bevor die erste Anweisung des Codes in der Laufzeit-Architektur ausgeführt werden. Dieses Ereignis ist immer eine Beenden-Ereignis. Wenn die Debugsitzung schrittweise ausführen, wird die IDE zu diesem Ereignis beendet.  
  
> [!NOTE]
>  Viele Sprachen werden globalen Initialisierer oder externe, vorkompilierte Funktionen (aus der CRT-Bibliothek oder _Main) am Anfang ihres Codes verwenden. Wenn die Sprache der das Programm debuggen enthält diesen Typen der Elemente vor den ersten Einstiegspunkt dieser Code ausgeführt wird und anschließend das punktereignis Eintrag wird gesendet. wenn der benutzerdefinierte Einstiegspunkt zeigen, wie z. B. **main** oder `WinMain`, erreicht wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Aktivieren eines Programms für das Debuggen](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)

