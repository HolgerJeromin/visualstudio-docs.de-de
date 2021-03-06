---
title: IDebugEventCallback2 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEventCallback2
helpviewer_keywords:
- IDebugEventCallback2
ms.assetid: 2c935ee0-2e22-4be0-a852-73736f33c8c9
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a140d5f0ecc2b250a8db4a2b78bfcc6544afd728
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47513633"
---
# <a name="idebugeventcallback2"></a>IDebugEventCallback2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDebugEventCallback2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugeventcallback2).  
  
Diese Schnittstelle wird von der Debug-Engine (DE) verwendet, um Debug-Ereignisse an die sitzungsbasierter Debug-Manager (SDM) zu senden.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugEventCallback2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] implementiert diese Schnittstelle zum Empfangen von Ereignissen aus einer Debug-Engine.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Eine Debug-Engine diese Schnittstelle in der Regel empfängt beim aufruft, des SDM [Anfügen](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [Anfügen](../../../extensibility/debugger/reference/idebugengine2-attach.md), oder [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md). Eine Debug-Engine sendet Ereignisse an das SDM, durch den Aufruf [Ereignis](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugEventCallback2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)|Sendet eine Benachrichtigung der Ereignisse an das SDM-Debuggen.|  
  
## <a name="remarks"></a>Hinweise  
 Obwohl [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) und [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) anzugeben, dass dafür ein `IDebugEventCallback2` -Schnittstelle, dies ist nicht der Fall ist, und der Schnittstellenzeiger wird immer ein null-Wert sein. Die Debug-Engine muss stattdessen die `IDebugEventCallback2` Schnittstelle empfangen, die im Aufruf von [Anfügen](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [Anfügen](../../../extensibility/debugger/reference/idebugengine2-attach.md), oder [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 Wenn ein Paket implementiert [IDebugEventCallback](../../../extensibility/debugger/reference/idebugeventcallback2.md) in verwaltetem Code, es wird dringend empfohlen, die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> aufgerufen werden, auf die verschiedenen Schnittstellen, die übergeben werden [Ereignis](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Anfügen](../../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [Anfügen](../../../extensibility/debugger/reference/idebugengine2-attach.md)

