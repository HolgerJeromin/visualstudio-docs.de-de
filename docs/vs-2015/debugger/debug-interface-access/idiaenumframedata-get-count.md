---
title: 'Idiaenumframedata:: Get_count | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::get_Count method
ms.assetid: 94374d27-e335-4e90-a442-233181ab8e58
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08dcb821536a49aee5e663920bb0893748be6d44
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47511883"
---
# <a name="idiaenumframedatagetcount"></a>IDiaEnumFrameData::get_Count
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [idiaenumframedata:: Get_count](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumframedata-get-count).  
  
Ruft die Anzahl der Frames-Datenelemente.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT get_Count (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 pRetVal  
 [out] Gibt die Anzahl der Frames-Datenelemente.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaEnumFrameData::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)



