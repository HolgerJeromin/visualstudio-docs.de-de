---
title: IEnumDebugBoundBreakpoints2::Clone | Microsoft-Dokumentation
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
- IEnumDebugBoundBreakpoints2::Clone
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2::Clone
ms.assetid: c6ce01a2-7da3-46ec-9837-855042fa7244
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 959e86563ff77907cecde265ce8e9a5bc1c110df
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514068"
---
# <a name="ienumdebugboundbreakpoints2clone"></a>IEnumDebugBoundBreakpoints2::Clone
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IEnumDebugBoundBreakpoints2::Clone](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugboundbreakpoints2-clone).  
  
Gibt eine Kopie der aktuellen Enumeration als ein separates Objekt zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT Clone(  
   IEnumDebugBoundBreakpoints2** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugBoundBreakpoints2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Gibt eine Kopie dieser Enumeration als ein separates Objekt zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Kopie der Enumeration hat den gleichen Zustand wie die ursprüngliche, zu dem Zeitpunkt, die diese Methode aufgerufen wird. Allerdings wird der Kopiervorgangs des und den ursprünglichen Zustand sind getrennt und einzeln geändert werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)

