---
title: IEEDataStorage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEEDataStorage
helpviewer_keywords:
- IEEDataStorage interface
ms.assetid: 704e932d-2325-410e-89c4-ce88c6ec19da
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aeb98c4c4d3b544616412b3cf5cf8a162fddbd6b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31120828"
---
# <a name="ieedatastorage"></a>IEEDataStorage
Diese Schnittstelle stellt ein Array von Bytes.  
  
## <a name="syntax"></a>Syntax  
  
```  
IEEDataStorage : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die ausdrucksauswertung (EE) implementiert diese Schnittstelle, um ein Array von Bytes darstellen (Typ-Schnellansichten, die zum Abrufen und Ändern von Daten über die [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) Schnittstelle). Die EE implementiert in der Regel diese Schnittstelle, um externen Typ-Schnellansichten unterstützen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Die Methoden für die `IPropertyProxyEESide` Schnittstelle, die alle diese-Schnittstelle zurückgeben. Rufen Sie [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) zum Abrufen der [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) Schnittstelle. Rufen Sie [QueryInterface](/cpp/atl/queryinterface) auf eine [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) Schnittstelle zum Abrufen der [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) Schnittstelle.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die `IEEDataStorage` Schnittstelle implementiert die folgenden Methoden:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)|Ruft die angegebene Anzahl von Datenbytes in einen angegebenen Puffer ab.|  
|[GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)|Ruft die Anzahl der Bytes verfügbar.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird von einer Schnellansicht Typ Zugriff auf Daten, die ein bestimmtes Objekt frei. Die Daten werden behandelt, als ein Array von Bytes, sodass der Typ-Schnellansicht, und bearbeiten es in beliebige Weise erforderlich, um es dem Benutzer angezeigt wird.  
  
 Ein benutzerdefinierter Viewer können auch diese Schnittstelle, falls gewünscht, obwohl in der Regel, ein benutzerdefinierter Viewer eine benutzerdefinierte Schnittstelle verwenden würden [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md) oder [GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md) (für Zeichenfolge-orientierte Daten).  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Core-Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [Typschnellansicht und benutzerdefinierter Viewer](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)