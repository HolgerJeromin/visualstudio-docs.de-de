---
title: DOCCONTEXT_COMPARE | Microsoft-Dokumentation
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
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1a4643a525e5a97f7c8af3be2e86eba9ac161936
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523307"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [DOCCONTEXT_COMPARE](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/doccontext-compare).  
  
Gibt die Kriterien zum Vergleichen von zwei dokumentenkontexte.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>Member  
 DOCCONTEXT_EQUAL  
 Finden Sie in der Liste, die den Zielkontext-Dokument entspricht der ersten Dokumentkontext.  
  
 DOCCONTEXT_LESS_THAN  
 Finden Sie in der Liste, die kleiner ist als den Zielkontext für das Dokument den ersten Dokumentenkontext.  
  
 DOCCONTEXT_GREATER_THAN  
 Finden Sie in der Liste, die über den Dokument-Zielkontext liegt der ersten Dokumentkontext.  
  
 DOCCONTEXT_SAME_DOCUMENT  
 Finden Sie in der Liste, die in demselben Dokument wie den Zielkontext für das Dokument ist der ersten Dokumentkontext.  
  
## <a name="remarks"></a>Hinweise  
 Übergeben als Argument an die [vergleichen](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) Methode.  
  
 Diese Werte werden verwendet, eine Vergleichskriterien für die Suche nach den ersten Dokumentenkontext in einer Liste an. Ein Dokumentenkontext erhält eine Liste der dokumentenkontexte selbst gegen durch Vergleichen der `IDebugDocumentContext2::Compare` Methode. Das erste Dokumentenkontext, in der Liste, die für die der Vergleichsoperator ist `true` wird zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)

