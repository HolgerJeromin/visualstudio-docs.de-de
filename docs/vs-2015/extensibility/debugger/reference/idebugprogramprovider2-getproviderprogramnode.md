---
title: IDebugProgramProvider2::GetProviderProgramNode | Microsoft-Dokumentation
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
- IDebugProgramProvider2::GetProviderProgramNode
helpviewer_keywords:
- IDebugProgramProvider2::GetProviderProgramNode
ms.assetid: e62e8e83-acbb-4c52-aedf-ffbd4670db29
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4e3909a1f294818b0030d30c4059ee6e01d7fec6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523106"
---
# <a name="idebugprogramprovider2getproviderprogramnode"></a>IDebugProgramProvider2::GetProviderProgramNode
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDebugProgramProvider2::GetProviderProgramNode](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode).  
  
Ruft die Programm-Knoten für ein bestimmtes Programm ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetProviderProgramNode(  
   PROVIDER_FLAGS       Flags,  
   IDebugDefaultPort2*  pPort,  
   AD_PROCESS_ID        processId,  
   REFGUID              guidEngine,  
   UINT64               programId,  
   IDebugProgramNode2** ppProgramNode  
);  
```  
  
```csharp  
int GetProviderProgramNode(  
   enum_PROVIDER_FLAGS    Flags,  
   IDebugDefaultPort2     pPort,  
   AD_PROCESS_ID          ProcessId,  
   ref Guid               guidEngine,  
   ulong                  programId,  
   out IDebugProgramNode2 ppProgramNode  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `Flags`  
 [in] Eine Kombination von Flags aus der [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md) Enumeration. Die folgenden Flags sind typisch für diesen Aufruf:  
  
|Flag|Beschreibung|  
|----------|-----------------|  
|`PFLAG_REMOTE_PORT`|Aufrufer wird auf dem Remotecomputer ausgeführt.|  
|`PFLAG_DEBUGGEE`|Aufrufer ist aktuell im Debugmodus befindlichen (Weitere Informationen über das marshalling von werden für jeden Knoten zurückgegeben werden).|  
|`PFLAG_ATTACHED_TO_DEBUGGEE`|Aufrufer wurde angefügt, aber nicht vom Debugger gestartet.|  
  
 `pPort`  
 [in] Der Port der aufrufende Prozess ausgeführt wird.  
  
 `processId`  
 [in] Ein [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) Struktur mit der betreffenden die ID des Prozesses, der das Programm enthält.  
  
 `guidEngine`  
 [in] GUID der Debug-Engine, der das Programm an (sofern vorhanden) angefügt ist.  
  
 `programId`  
 [in] Die ID des Programms für das Programm Knotens abgerufen.  
  
 `ppProgramNode`  
 [out] Ein [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) Objekt, das den angeforderten Programms-Knoten darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

