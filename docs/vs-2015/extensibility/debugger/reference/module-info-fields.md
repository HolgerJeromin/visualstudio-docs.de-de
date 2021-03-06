---
title: MODULE_INFO_FIELDS | Microsoft-Dokumentation
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
- MODULE_INFO_FIELDS
helpviewer_keywords:
- MODULE_INFO_FIELDS enumeration
ms.assetid: 8bed85f4-235f-4192-b58f-5fad7a4d7a78
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a6b5e1e820dc63c2f771eadf89c1afd0b0e8e3c0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47513574"
---
# <a name="moduleinfofields"></a>MODULE_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [MODULE_INFO_FIELDS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/module-info-fields).  
  
Gibt die Flags für die Debuginformationen für das Modul an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_MODULE_INFO_FIELDS {   
   MIF_NONE              = 0x0000,  
   MIF_NAME              = 0x0001,  
   MIF_URL               = 0x0002,  
   MIF_VERSION           = 0x0004,  
   MIF_DEBUGMESSAGE      = 0x0008,  
   MIF_LOADADDRESS       = 0x0010,  
   MIF_PREFFEREDADDRESS  = 0x0020,  
   MIF_SIZE              = 0x0040,  
   MIF_LOADORDER         = 0x0080,  
   MIF_TIMESTAMP         = 0x0100,  
   MIF_URLSYMBOLLOCATION = 0x0200,  
   MIF_FLAGS             = 0x0400,  
   MIF_ALLFIELDS         = 0x07ff  
};  
typedef DWORD MODULE_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_MODULE_INFO_FIELDS {   
   MIF_NONE              = 0x0000,  
   MIF_NAME              = 0x0001,  
   MIF_URL               = 0x0002,  
   MIF_VERSION           = 0x0004,  
   MIF_DEBUGMESSAGE      = 0x0008,  
   MIF_LOADADDRESS       = 0x0010,  
   MIF_PREFFEREDADDRESS  = 0x0020,  
   MIF_SIZE              = 0x0040,  
   MIF_LOADORDER         = 0x0080,  
   MIF_TIMESTAMP         = 0x0100,  
   MIF_URLSYMBOLLOCATION = 0x0200,  
   MIF_FLAGS             = 0x0400,  
   MIF_ALLFIELDS         = 0x07ff  
};  
```  
  
## <a name="members"></a>Member  
 MIF_NONE  
 Verwenden Sie Initialize/keines der Felder in der Struktur.  
  
 MIF_NAME  
 Initialisieren und Verwenden der `m_bstrName` -Feld in der [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) Struktur.  
  
 MIF_URL  
 Initialisieren und Verwenden der `m_bstrUrl` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_VERSION  
 Initialisieren und Verwenden der `m_bstrVersion` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_DEBUGMESSAGE  
 Initialisieren und Verwenden der `m_bstrDebugMessage` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_LOADADDRESS  
 Initialisieren und Verwenden der `m_addrLoadAddress` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_PREFFEREDADDRESS  
 Initialisieren und Verwenden der `m_addrPreferredLoadAddress` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_SIZE  
 Initialisieren und Verwenden der `m_dwSize` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_LOADORDER  
 Initialisieren und Verwenden der `m_dwLoadOrder` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_TIMESTAMP  
 Initialisieren und Verwenden der `m_TimeStamp` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_URLSYMBOLLOCATION  
 Initialisieren und Verwenden der `m_bstrUrlSymbolLocation` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_FLAGS  
 Initialisieren und Verwenden der `m_dwModuleFlags` -Feld in der `MODULE_INFO` Struktur.  
  
 MIF_ALLFIELDS  
 Initialize/verwenden alle Felder in der `MODULE_INFO` Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Diese Werte werden übergeben, als Argument an die [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md) Methode, um die Felder anzugeben der [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) sind, dass die Struktur initialisiert werden.  
  
 Diese Werte werden auch verwendet, der `MODULE_INFO` Struktur, um anzugeben, welche Felder verwendet und gültig sind.  
  
 Diese Flags können kombiniert werden, mit einer bitweisen `OR`.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)

