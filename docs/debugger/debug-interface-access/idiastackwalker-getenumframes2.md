---
title: IDiaStackWalker::getEnumFrames2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames2 method
ms.assetid: 73196d3f-112c-4b3a-997b-7c6b815d4afc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 834b202d406ce7ae2e2a5b2ec80b8f7c46f0f576
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
ms.locfileid: "31461372"
---
# <a name="idiastackwalkergetenumframes2"></a>IDiaStackWalker::getEnumFrames2
Ruft eine Stack-Frame-Enumerator für eine bestimmte Plattform-Typ ab.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
  
      HRESULT getEnumFrames2(   
   enum  CV_CPU_TYPE_e    cpuid,  
   IDiaStackWalkHelper*   pHelper,  
   IDiaEnumStackFrames**  ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cpuid`  
 [in] Ein Wert aus der [CV_CPU_TYPE_e-Enumeration](../../debugger/debug-interface-access/cv-cpu-type-e.md) Enumeration, die den Plattformtyp angeben.  
  
 `pHelper`  
 [in] Das Hilfsobjekt [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) Objekt.  
  
 `ppEnum`  
 [out] Gibt eine [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md) mit einer Liste von Objekt [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md) Objekte.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Eine Liste der Stapel Frame nur die X86 abrufen Plattform, rufen die [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)   
 [CV_CPU_TYPE_e-Enumeration](../../debugger/debug-interface-access/cv-cpu-type-e.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)