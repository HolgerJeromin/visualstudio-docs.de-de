---
title: 'Idiasymbol:: Get_machinetype | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_machineType method
ms.assetid: 30870b10-6f32-45c6-a0d7-020dea707710
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f001450f874969007e5f592824bc1a9d693e1cac
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
ms.locfileid: "31464120"
---
# <a name="idiasymbolgetmachinetype"></a>IDiaSymbol::get_machineType
Ruft den Typ der Ziel-CPU ab.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
HRESULT get_machineType (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Gibt einen Wert aus der [CV_CPU_TYPE_e-Enumeration](../../debugger/debug-interface-access/cv-cpu-type-e.md) -Enumeration, die das Ziel-CPU-Typ angibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls gibt `S_FALSE` oder ein Fehlercode.  
  
> [!NOTE]
>  Ein Rückgabewert von `S_FALSE` bedeutet, dass die Eigenschaft ist nicht verfügbar für das Symbol.  
  
## <a name="see-also"></a>Siehe auch  
 [CV_CPU_TYPE_e-Enumeration](../../debugger/debug-interface-access/cv-cpu-type-e.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)