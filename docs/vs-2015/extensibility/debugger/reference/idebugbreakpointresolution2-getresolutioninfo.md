---
title: IDebugBreakpointResolution2::GetResolutionInfo | Microsoft-Dokumentation
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
- IDebugBreakpointResolution2::GetResolutionInfo
helpviewer_keywords:
- IDebugBreakpointResolution2::GetResolutionInfo
ms.assetid: 828cbdf6-b87d-4c45-be87-d87087b04a60
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ece39f8fcd042fa5b20b3094759ba515ada56d0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47522369"
---
# <a name="idebugbreakpointresolution2getresolutioninfo"></a>IDebugBreakpointResolution2::GetResolutionInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDebugBreakpointResolution2::GetResolutionInfo](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo).  
  
Ruft die Informationen der Haltepunkt-Lösung, die diesem Breakpoint beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT GetResolutionInfo(   
   BPRESI_FIELDS       dwFields,  
   BP_RESOLUTION_INFO* pBPResolutionInfo  
);  
```  
  
```csharp  
int GetResolutionInfo(   
   enum BPRESI_FIELDS   dwFields,  
   BP_RESOLUTION_INFO[] pBPResolutionInfo  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwFields`  
 [in] Eine Kombination von Flags aus der [BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md) Enumeration, die bestimmen, welche Felder von der `pBPResolutionInfo` sind, dass Parameter ausgefüllt werden müssen.  
  
 `pBPResolutionInfo`  
 [out] Die [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) Struktur mit Informationen zu diesem Haltepunkt gefüllt werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`; gibt andernfalls einen Fehlercode zurück.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel implementiert diese Methode für eine einfache `CDebugBreakpointResolution` -Objekt, das macht die [IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md) Schnittstelle.  
  
```  
HRESULT CDebugBreakpointResolution::GetResolutionInfo(  
   BPRESI_FIELDS dwFields,  
   BP_RESOLUTION_INFO* pBPResolutionInfo)  
{    
   HRESULT hr;    
  
   if (pBPResolutionInfo)    
   {    
      // Copy the specified fields of the request information from the class  
      // member variable to the local BP_RESOLUTION_INFO variable.    
      hr = CopyBP_RESOLUTION_INFO(m_bpResolutionInfo,  
                                  *pBPResolutionInfo,  
                                  dwFields);    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
  
HRESULT CDebugBreakpointResolution::CopyBP_RESOLUTION_INFO(  
   BP_RESOLUTION_INFO& bpResSrc,  
   BP_RESOLUTION_INFO& bpResDest,  
   DWORD dwFields)    
{    
   HRESULT hr = S_OK;    
  
   // Start with a raw copy.    
   memcpy(&bpResDest, &bpResSrc, sizeof(BP_RESOLUTION_INFO));    
  
   // The fields in the destination is the result of the AND of  
   //  bpInfoSrc.dwFields and dwFields.    
   bpResDest.dwFields = dwFields & bpResSrc.dwFields;    
  
   // Fill in the bp location information if the BPRESI_BPRESLOCATION  
   //  flag is set in BPRESI_FIELDS.    
   if (IsFlagSet(bpResDest.dwFields, BPRESI_BPRESLOCATION))    
   {    
      // Switch based on the BP_TYPE.     
      switch (bpResSrc.bpResLocation.bpType)    
      {    
         case BPT_CODE:    
         {    
            // AddRef the IDebugCodeContext2 of the BP_RESOLUTION_CODE structure.    
            bpResDest.bpResLocation.bpResLocation.bpresCode.pCodeContext->AddRef();    
            break;    
         }    
         case BPT_DATA:    
         {    
            // Copy the bstrDataExpr, bstrFunc, and bstrImage of the  
            // BP_RESOLUTION_DATA structure.    
            bpResDest.bpResLocation.bpResLocation.bpresData.bstrDataExpr =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrDataExpr);    
            bpResDest.bpResLocation.bpResLocation.bpresData.bstrFunc =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrFunc);    
            bpResSrc.bpResLocation.bpResLocation.bpresData.bstrImage =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrImage);    
            break;    
         }    
         default:    
         {    
            assert(FALSE);    
            // Clear the BPRESI_BPRESLOCATION flag in the BPRESI_FIELDS  
            // of the destination BP_RESOLUTION_INFO.    
            ClearFlag(bpResDest.dwFields, BPRESI_BPRESLOCATION);    
            break;    
         }    
      }    
   }    
   // AddRef the IDebugProgram2 if the BPRESI_PROGRAM flag is set in BPRESI_FIELDS.  
   if (IsFlagSet(bpResDest.dwFields, BPRESI_PROGRAM))    
   {    
      bpResDest.pProgram->AddRef();    
   }    
   // AddRef the IDebugThread2 if the BPRESI_THREAD flag is set in BPRESI_FIELDS.  
   if (IsFlagSet(bpResDest.dwFields, BPRESI_THREAD))    
   {    
      bpResDest.pThread->AddRef();    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)   
 [BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)

