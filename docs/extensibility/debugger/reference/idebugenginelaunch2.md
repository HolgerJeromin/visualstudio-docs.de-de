---
title: IDebugEngineLaunch2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineLaunch2
helpviewer_keywords:
- IDebugEngineLaunch2 interface
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1abff9f393b34bbf5950c9e56b6f489f332840db
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31113246"
---
# <a name="idebugenginelaunch2"></a>IDebugEngineLaunch2
Von einer Debugging-Modul (DE) verwendet zum Starten und Beenden von Programmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugEngineLaunch2 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Diese Schnittstelle wird durch eine benutzerdefinierte DE implementiert, weist besondere Anforderungen für das Starten eines Prozesses, das vollständig von einem benutzerdefinierten Port nicht behandelt werden kann. Dies ist normalerweise der Fall, wenn DE Teil einer Interpreter ist und der zu debuggende Prozess ein Skript ist: der Interpreter muss zuerst gestartet werden, und klicken Sie dann das Skript geladen und gestartet wird. Ein Port den Interpreter starten kann, aber das Skript möglicherweise erfordern eine besondere Behandlung (das ist, in dem die DE eine Rolle verfügt). Diese Schnittstelle wird implementiert, nur, wenn es sind besondere Anforderungen für das Starten eines Programms, das ein benutzerdefinierter Port verarbeitet werden kann.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Diese Schnittstelle wird aufgerufen, von der Sitzung Debug-Manager (SDM) Wenn die SDM diese Schnittstelle abrufen kann aus der [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) Schnittstelle (mithilfe von QueryInterface). Wenn diese Schnittstelle abgerufen werden kann, weiß der SDM an, dass die DE besondere Anforderungen gelten, und diese Schnittstelle ruft, um das Programm, anstatt den Port, die Ausführung zu starten.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugEngineLaunch2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|Startet einen Prozess mithilfe der Deutschland.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|Setzt Verarbeitung Ausführung.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|Bestimmt, ob ein Prozess beendet werden kann.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|Beendet einen Prozess an.|  
  
## <a name="requirements"></a>Anforderungen  
 Header: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)