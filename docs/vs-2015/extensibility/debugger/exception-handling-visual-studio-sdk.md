---
title: Ausnahmebehandlung (Visual Studio SDK) | Microsoft-Dokumentation
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
- debugging [Debugging SDK], exception handling
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e42e4dbe18b0d2fe6da522d24d493270518e884e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524418"
---
# <a name="exception-handling-visual-studio-sdk"></a>Ausnahmebehandlung (Visual Studio SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Ausnahmebehandlung (Visual Studio SDK)](https://docs.microsoft.com/visualstudio/extensibility/debugger/exception-handling-visual-studio-sdk).  
  
Im folgenden wird beschrieben, den Prozess, der auftritt, wenn Ausnahmen ausgelöst werden.  
  
## <a name="exception-handling-process"></a>Ausnahme Behandlungsvorgangs  
  
1.  Zuerst wird eine Ausnahme ausgelöst, aber bevor sie vom Ausnahmehandler in der Anwendung im Debugmodus befindlichen behandelt wird, die Debug-Engine (DE sendet) eine [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) für die Sitzung-Debug-Manager (SDM) als eine Beenden-Ereignis. Die `IDebugExceptionEvent2` wird gesendet, wenn nur die Einstellungen für die Ausnahme (angegeben in das Dialogfeld "Ausnahmen" in das debugpaket) angeben, dass der Benutzer auf Benachrichtigungen über Ausnahmefehler der ersten Chance beenden möchte.  
  
2.  Die SDM-Aufrufe [IDebugExceptionEvent2::GetException](../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) -Eigenschaft der Ausnahme abgerufen.  
  
3.  Ruft die Debug-Paket [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) um zu bestimmen, welche Optionen Sie dem Benutzer.  
  
4.  Das debugpaket fordert den Benutzer, wie Sie die Ausnahme zu behandeln, durch Öffnen eines Dialogfelds Ausnahmefehler der ersten Chance.  
  
5.  Wenn der Benutzer auswählt, um den Vorgang fortzusetzen, das SDM ruft [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md).  
  
    -   Wenn die Methode S_OK zurückgibt, ruft [IDebugExceptionEvent2::PassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md).  
  
         - oder -   
  
         Wenn die Methode gibt S_FALSE zurück, das Programm zurück, im Debugmodus befindlichen erhält eine zweite Chance, die die Ausnahme zu behandeln.  
  
6.  Verfügt das derzeit debuggte Programm kein Handler für eine zweite Chance-Ausnahme, die DE sendet eine `IDebugExceptionEvent2` , das SDM als **EVENT_SYNC_STOP**.  
  
7.  Das debugpaket fordert den Benutzer, wie Sie die Ausnahme zu behandeln, durch Öffnen eines Dialogfelds Ausnahmefehler der ersten Chance.  
  
8.  Ruft die Debug-Paket [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) um zu bestimmen, welche Optionen Sie dem Benutzer.  
  
9. Das debugpaket fordert den Benutzer, wie Sie die Ausnahme zu behandeln, indem Sie eine zweite Chance Ausnahme-Dialogfeld zu öffnen.  
  
10. Wenn die Methode S_OK zurückgibt, ruft `IDebugExceptionEvent2::PassToDebuggee`.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufen von Debuggerereignissen](../../extensibility/debugger/calling-debugger-events.md)

