---
title: EVENTATTRIBUTES | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 87d6a2176dcd3c4cf748549f94d071b181d0d14f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103928"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
Gibt die Attribute des Ereignisses.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```csharp  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## <a name="members"></a>Member  
 EVENT_ASYNCHRONOUS  
 Gibt an, dass das Ereignis asynchron ist und keine Antwort auf das Ereignis ist erforderlich.  
  
 EVENT_SYNCHRONOUS  
 Gibt an, dass das Ereignis synchron ist. anhand der Antworten [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).  
  
 EVENT_STOPPING  
 Gibt an, dass dies eine Stopping-Ereignis. Muss zusammen mit entweder `EVENT_ASYNCHRONOUS` oder `EVENT_SYNCHRONOUS`.  
  
 EVENT_ASYNC_STOP  
 Gibt eine asynchrone Stopping-Ereignis an. Es ist derzeit kein entsprechendes Ereignis. Dieses Kennzeichen ist nur ein Platzhalter.  
  
 EVENT_SYNC_STOP  
 Gibt eine synchrone Stopping-Ereignis (eine Kombination von `EVENT_SYNCHRONOUS` und `EVENT_STOPPING`). Dieser Wert wird verwendet, durch ein Debugging-Modul (DE) beim Senden einer Stopping-Ereignis. Die Antwort erfolgt durch einen Aufruf von [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [Schritt](../../../extensibility/debugger/reference/idebugprogram2-step.md), oder [Fortfahren](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
 EVENT_IMMEDIATE  
 Gibt an, ein Ereignis, das für die IDE sofort und synchron gesendet wird. Dieses Flag wird kombiniert mit anderen Flags wie `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, oder `EVENT_SYNC_STOP` an, dass der Typ des Ereignisses und die Tatsache, dass die Antwort-Mechanismus (sofern vorhanden) bekannt ist.  
  
 EVENT_EXPRESSION_EVALUATION  
 Das Ereignis ist das Ergebnis der Auswertung von Ausdrücken.  
  
## <a name="remarks"></a>Hinweise  
 Diese Werte werden übergeben, die `dwAttrib` Parameter von der [Ereignis](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) Methode.  
  
 Diese Werte können kombiniert werden, mit einem bitweisen `OR`.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)