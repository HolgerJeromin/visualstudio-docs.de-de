---
title: IEnumDebugFields::GetCount | Microsoft-Dokumentation
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
- IEnumDebugFields::GetCount
helpviewer_keywords:
- IEnumDebugFields::GetCount method
ms.assetid: 3f471b40-4db3-49f7-b504-58b2476eef74
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 768aef20f89866d90fd71d2c13c559b19920279a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47520977"
---
# <a name="ienumdebugfieldsgetcount"></a>IEnumDebugFields::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IEnumDebugFields::GetCount](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugfields-getcount).  
  
Diese Methode gibt die Anzahl der Elemente in der Enumeration.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT GetCount(  
   [out] ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pcelt`  
 [out] Gibt die Anzahl der Elemente in der Enumeration zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist nicht Teil der übliche COM-Enumerationsschnittstelle gibt an, dass nur weiter, Klonen, überspringen und Zurücksetzen der implementiert werden müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)

