---
title: Implementieren von GetMethodProperty | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetMethodProperty method
- IDebugExpressionEvaluator2 property
ms.assetid: 6305874f-a2c4-4432-834c-07530ea84bff
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4e34101ec3e751414fa360c39fde748bd07124b3
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231516"
---
# <a name="implement-getmethodproperty"></a>Implementieren von GetMethodProperty
> [!IMPORTANT]
>  In Visual Studio 2015 ist diese Art der Implementierung von ausdrucksauswertungen veraltet. Informationen zum Implementieren von CLR-ausdrucksauswertungen finden Sie unter [CLR ausdrucksauswertungen](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) und [Auswertung (Beispiel) verwaltete Ausdruck](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Ruft der Debug-Engine des (DE) für Visual Studio [GetDebugProperty](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md), die wiederum ruft [von GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) zum Abrufen von Informationen über die aktuelle Methode auf dem Stapelrahmen.  
  
 Diese Implementierung der `IDebugExpressionEvaluator::GetMethodProperty` führt die folgenden Aufgaben:  
  
1.  Aufrufe [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md), und übergeben Sie die [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) Objekt. Die symbolanbieter (SP) gibt eine [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) , die die Methode, die die angegebene Adresse enthält darstellt.  
  
2.  Ruft die [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) aus der `IDebugContainerField`.  
  
3.  Instanziiert die Klasse (namens `CFieldProperty` in diesem Beispiel), implementiert die [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) Schnittstelle und enthält die `IDebugMethodField` Objekt zurückgegeben wird, von SP  
  
4.  Gibt die `IDebugProperty2` -Schnittstelle aus der `CFieldProperty` Objekt.  
  
## <a name="managed-code"></a>Verwalteter Code  
 Dieses Beispiel zeigt eine Implementierung von `IDebugExpressionEvaluator::GetMethodProperty` in verwaltetem Code.  
  
```csharp  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        public HRESULT GetMethodProperty(  
                IDebugSymbolProvider symbolProvider,  
                IDebugAddress        address,  
                IDebugBinder         binder,  
                int                  includeHiddenLocals,  
            out IDebugProperty2      property)   
        {  
            IDebugContainerField containerField = null;  
            IDebugMethodField methodField       = null;  
            property = null;  
  
            // Get the containing method field.  
            symbolProvider.GetContainerField(address, out containerField);  
            methodField = (IDebugMethodField) containerField;  
  
            // Return the property of method field.  
            property = new CFieldProperty(symbolProvider, address, binder, methodField);  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Nicht verwalteter code  
 Dieses Beispiel zeigt eine Implementierung von `IDebugExpressionEvaluator::GetMethodProperty` in nicht verwaltetem Code.  
  
```  
[CPP]  
STDMETHODIMP CExpressionEvaluator::GetMethodProperty(  
        in IDebugSymbolProvider *pprovider,  
        in IDebugAddress        *paddress,  
        in IDebugBinder         *pbinder,  
        in BOOL                  includeHiddenLocals,  
        out IDebugProperty2    **ppproperty  
    )  
{  
    if (pprovider == NULL)  
        return E_INVALIDARG;  
  
    if (ppproperty == NULL)  
        return E_INVALIDARG;  
    else  
        *ppproperty = 0;  
  
    HRESULT hr;  
    IDebugContainerField* pcontainer = NULL;  
  
    hr = pprovider->GetContainerField(paddress, &pcontainer);  
    if (FAILED(hr))  
        return hr;  
  
    IDebugMethodField*    pmethod    = NULL;  
    hr = pcontainer->QueryInterface( IID_IDebugMethodField,  
            reinterpret_cast<void**>(&pmethod));  
    pcontainer->Release();  
    if (FAILED(hr))  
        return hr;  
  
    CFieldProperty* pfieldProperty = new CFieldProperty( pprovider,  
                                                         paddress,  
                                                         pbinder,  
                                                         pmethod );  
    pmethod->Release();  
    if (!pfieldProperty)  
        return E_OUTOFMEMORY;  
  
    hr = pfieldProperty->Init();  
    if (FAILED(hr))  
    {  
        pfieldProperty->Release();  
        return hr;  
    }  
  
    hr = pfieldProperty->QueryInterface( IID_IDebugProperty2,  
            reinterpret_cast<void**>(ppproperty));  
    pfieldProperty->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Beispielimplementierung von lokalen Elementen](../../extensibility/debugger/sample-implementation-of-locals.md)