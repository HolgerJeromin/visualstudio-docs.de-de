---
title: IPropertyProxyEESide::GetManagedViewerCreationData | Microsoft-Dokumentation
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
- IPropertyProxyEESide::GetManagedViewerCreationData
helpviewer_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 90087bfad956427ef3ff59fd7ffdc8b92c9f5687
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47522223"
---
# <a name="ipropertyproxyeesidegetmanagedviewercreationdata"></a>IPropertyProxyEESide::GetManagedViewerCreationData
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IPropertyProxyEESide::GetManagedViewerCreationData](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata).  
  
Ruft Informationen zu den Viewer für diesen Eigenschaftentyp um Instanziieren dieser Viewer ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT GetManagedViewerCreationData(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  className,  
   ASSEMBLYLOCRESOLUTION* alr,  
   BOOL*                  replacementOk  
);  
```  
  
```csharp  
int GetManagedViewerCreationData(  
   out string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     className,  
   out enum_ASSEMBLYLOCRESOLUTION alr,  
   out int                        replacementOk  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `assemName`  
 [out] Gibt den Namen der Assembly, die dieses Objekt enthält.  
  
 `assemBytes`  
 [out] Gibt eine [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) -Objekt, das die Assemblybytes dieses Objekts (Dies ist ein null-Wert, wenn keine Bytes verfügbar sind) enthält.  
  
 `assemPdb`  
 [out] Gibt eine `IEEDataStorage` Objektspeicher, die Symbol enthält Informationen für dieses Objekt (Dies ist ein null-Wert, wenn kein Symbolspeicher verfügbar ist).  
  
 `className`  
 [out] Gibt den Namen der Klasse, die dieses Objekt zurück.  
  
 `alr`  
 [out] Gibt einen Wert aus der [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) Enumeration, die den Speicherort der Assembly angibt.  
  
 `replacementOk`  
 [out] Ungleich NULL zurückgibt (`TRUE`), wenn der Wert des Objekts geändert werden kann; NULL (`FALSE`), wenn das Objekt schreibgeschützt ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Typ-Schnellansichten verwendet, um einen verwalteten Viewer zu instanziieren.  
  
## <a name="see-also"></a>Siehe auch  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)

