---
title: MESSAGETYPE | Microsoft-Dokumentation
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
- MESSAGETYPE
helpviewer_keywords:
- MESSAGETYPE enumeration
ms.assetid: 800cc77d-3c27-4763-a9df-552a9384bd49
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f4e6bb32aa3387d79ea233e8751c5805537947fe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47511929"
---
# <a name="messagetype"></a>MESSAGETYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [MESSAGETYPE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/messagetype).  
  
Gibt den Nachrichtentyp und dem Grund.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
typedef DWORD MESSAGETYPE;  
```  
  
```csharp  
public enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
```  
  
## <a name="members"></a>Member  
 MT_OUTPUTSTRING  
 Gibt an, dass die Meldung im Ausgabefenster gesendet werden soll. Dies ist von sich gegenseitig ausschließende `MT_MESSAGEBOX`.  
  
 MT_MESSAGEBOX  
 Gibt an, dass die Nachricht in einem Meldungsfeld angezeigt werden soll. Dies ist von sich gegenseitig ausschließende `MT_OUTPUTSTRING`.  
  
 MT_TYPE_MASK  
 Ein-Wert, das Ziel für die Nachricht zu isolieren.  
  
 MT_REASON_EXCEPTION  
 Gibt an, dass als Ergebnis einer Ausnahme ein Meldungsfeld angezeigt wird. Dies ist von sich gegenseitig ausschließende `MT_REASON_TRACEPOINT`.  
  
 MT_REASON_TRACEPOINT  
 Gibt an, dass als Ergebnis einen Ablaufverfolgungspunkt erreicht ein Meldungsfeld angezeigt wird. Dies ist an sich gegenseitig ausschließende `MT_REASON_EXCEPTION`.  
  
 MT_REASON_MASK  
 Ein-Wert, den Grund für die anzuzeigende Nachricht zu isolieren.  
  
## <a name="remarks"></a>Hinweise  
 Diese Werte werden zurückgegeben, aus der ["GetMessage"](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md) und [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md) Methoden.  
  
 Der Grund-Werte kann kombiniert werden, mit einem der die Ziel-Ausgabewerte, die mit einer bitweisen `OR`.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 ["GetMessage"](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)   
 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md)

