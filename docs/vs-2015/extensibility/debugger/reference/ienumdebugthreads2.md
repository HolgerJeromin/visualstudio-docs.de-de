---
title: IEnumDebugThreads2 | Microsoft-Dokumentation
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
- IEnumDebugThreads2
helpviewer_keywords:
- IEnumDebugThreads2
ms.assetid: 1854f078-3b49-42c2-b65b-33e3b506fd63
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 96a86c322ed2fa1ac750171116a0a11c9b2b4d99
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47512158"
---
# <a name="ienumdebugthreads2"></a>IEnumDebugThreads2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IEnumDebugThreads2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugthreads2).  
  
Diese interfac genannt Listet die Threads in der aktuellen Debuggingsitzung ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
IEnumDebugThreads2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debug-Engine (DE) implementiert diese Schnittstelle, um eine Liste der Threads in einem Programm darstellen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Rufen Sie [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md) beim Abrufen der diese Schnittstelle, die eine Liste aller Threads in allen Programmen, die in einem Prozess repräsentieren. Rufen Sie [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) beim Abrufen der diese Schnittstelle, die eine Liste der Threads, die in einem Programm darstellt.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IEnumDebugThreads2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Nächste](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md)|Ruft eine angegebene Anzahl von Threads in der Enumerationsfolge ab.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugthreads2-skip.md)|Überspringt eine angegebene Anzahl von Threads in einer Enumerationsfolge.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugthreads2-reset.md)|Setzt eine Enumerationsfolge auf den Anfang zurück.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugthreads2-clone.md)|Erstellt einen Enumerator, der den gleichen Enumerationszustand wie der aktuelle enthält.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugthreads2-getcount.md)|Ruft die Anzahl der Threads in einen Enumerator ab.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Studio in der Regel ruft diese Schnittstelle zum Aktualisieren der **Threads** Fenster auch hinsichtlich den ersten Thread, der Liste zu erhalten, um aufzurufen [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md), [Weiter](../../../extensibility/debugger/reference/idebugprocess3-continue.md), und [Schritt](../../../extensibility/debugger/reference/idebugprocess3-step.md).  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)   
 [Schritt](../../../extensibility/debugger/reference/idebugprocess3-step.md)   
 [Fortsetzen](../../../extensibility/debugger/reference/idebugprocess3-continue.md)   
 [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md)

