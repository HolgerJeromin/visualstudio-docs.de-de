---
title: 'Ienumjsstackframes:: Next-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumJsStackFrames.Next
apilocation:
- jscript9diag.dll
ms.assetid: efceb3a1-9239-4f55-9cbb-94670679988b
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2068bd130e7eb03747b89e2ba107019aa1cd458
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
ms.locfileid: "24727710"
---
# <a name="ienumjsstackframesnext-method"></a>IEnumJsStackFrames::Next-Methode
Ruft die angegebene Anzahl an Frames ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next(  
   ULONG cFrameCount,  
   JS_NATIVE_FRAME *pFrames,  
   ULONG *pcFetched  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cFrameCount`  
 [in] Die Anzahl der abzurufenden Frames.  
  
 `pFrames`  
 [out] Das Array, um die Frames zu speichern.  
  
 `pcFetched`  
 [out] Die Anzahl der zurückgegebenen Frames.  
  
## <a name="return-value"></a>Rückgabewert  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "jscript9diag.h"  
  
## <a name="see-also"></a>Siehe auch  
 [IEnumJsStackFrames-Schnittstelle](../../winscript/reference/ienumjsstackframes-interface.md)