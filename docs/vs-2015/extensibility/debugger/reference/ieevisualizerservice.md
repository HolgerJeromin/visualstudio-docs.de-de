---
title: IEEVisualizerService | Microsoft-Dokumentation
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
- IEEVisualizerService
helpviewer_keywords:
- IEEVisualizerService interface
ms.assetid: 3bdb124b-c582-47ba-b465-13c6a1cdb702
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 76e0ea47c1bfaea9bac96b3faacc3a01403f829d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47521199"
---
# <a name="ieevisualizerservice"></a>IEEVisualizerService
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IEEVisualizerService](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerservice).  
  
> [!IMPORTANT]
>  In Visual Studio 2015 ist diese Art der Implementierung von ausdrucksauswertungen veraltet. Informationen zu CLR-ausdrucksauswertungen implementieren, finden Sie unter [CLR Ausdrucksauswertungen](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) und [Managed Expression Evaluator Sample](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Diese Schnittstelle implementiert, wichtige Methoden, die Funktionalität zum Angeben der [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) und [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) Schnittstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
IEEVisualizerService : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Visual Studio implementiert diese Schnittstelle, um eine ausdrucksauswertung (EE), um Typ-Schnellansichten unterstützen können.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Die Aufrufe EE [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md) Sie diese Schnittstelle als Teil der Unterstützung für Typ-Schnellansichten zu erhalten.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md)|Ruft die Anzahl der benutzerdefinierten Viewer, die diesen Dienst bekannt sind.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)|Ruft die Liste der benutzerdefinierten Viewer ab.|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)|Gibt ein Proxyobjekt für eine Eigenschaft zurück.|  
|[GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)|Ruft die Anzahl der Zeichenfolgen, die für die angegebene Eigenschaft oder das Feld angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Die IDE verwendet das [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) Schnittstelle, um zu bestimmen, ob alle benutzerdefinierten Viewer oder geben Sie die Schnellansichten für die Eigenschaft. Durch das Erstellen einer Schnellansicht-Diensts (mit [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)), die EE kann die Funktionalität zum Angeben der `IDebugProperty3` und [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) (die unterstützt werden, anzeigen und Ändern einer Eigenschaftswert)-Schnittstellen und Typ-Schnellansichten und zu unterstützen.  
  
 Verfügt ein EE benutzerdefinierten Viewer, die selbst implementiert, fügen Sie die EE kann die `CLSID`s, der diesen benutzerdefinierten Viewer an das Ende der Liste, die vom [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md). Dies ermöglicht eine EE Unterstützung von typschnellansichten und einen eigenen benutzerdefinierten Viewern. Müssen nur darauf achten, [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) gibt alle benutzerdefinierten Viewer hinzufügen.  
  
 Finden Sie unter [Typschnellansicht und benutzerdefinierte Viewer](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) eine Erläuterung des Unterschieds zwischen Schnellansichten und -Viewer.  
  
## <a name="requirements"></a>Anforderungen  
 Header: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Schnittstellen für die Ausdrucksauswertung](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)   
 [Typschnellansicht und benutzerdefinierter Viewer](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)

