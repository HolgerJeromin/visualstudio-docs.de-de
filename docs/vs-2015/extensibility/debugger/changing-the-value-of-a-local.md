---
title: Ändern des Werts eines lokalen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, changing values programmatically
ms.assetid: 8407d3df-d38a-4328-82d1-98084bef43ec
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b24bf833336245ff36384e3f34d83b27ed44a62c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47515494"
---
# <a name="changing-the-value-of-a-local"></a>Ändern des Werts eines lokalen Elements
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Ändern des Werts eines lokalen Elements](https://docs.microsoft.com/visualstudio/extensibility/debugger/changing-the-value-of-a-local).  
  
> [!IMPORTANT]
>  In Visual Studio 2015 ist diese Art der Implementierung von ausdrucksauswertungen veraltet. Informationen zu CLR-ausdrucksauswertungen implementieren, finden Sie unter [CLR Ausdrucksauswertungen](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) und [Managed Expression Evaluator Sample](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Wenn ein neuer Wert eingegeben wird, klicken Sie im Feld mit Wert der **"lokal"** Fenster, das debugpaket übergibt die Zeichenfolge wie eingegeben werden, um die ausdrucksauswertung (EE). Die EE wertet diese Zeichenfolge, die kann entweder einen einfachen Wert oder einen Ausdruck enthalten, und speichert den resultierenden Wert in der zugehörigen lokalen.  
  
 Dies ist eine Übersicht über den Prozess zum Ändern des Werts eines lokalen Elements:  
  
1.  Nachdem der neue Wert eingegeben wurde, ruft Visual Studio [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) auf die [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) Objekt, mit der lokalen verknüpft ist.  
  
2.  `IDebugProperty2::SetValueAsString` führt folgende Ausgaben aus:  
  
    1.  Wertet die Zeichenfolge, um einen Wert zu erzeugen.  
  
    2.  Bindet das zugeordnete [IDebugField](../../extensibility/debugger/reference/idebugfield.md) Objekt zum Abrufen einer [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) Objekt.  
  
    3.  Konvertiert den Wert in eine Reihe von Bytes an.  
  
    4.  Aufrufe [SetValue](../../extensibility/debugger/reference/idebugobject-setvalue.md) den Wert des Bytes in den Arbeitsspeicher eingefügt wird, damit das derzeit debuggte Programm darauf zugreifen kann.  
  
3.  Visual Studio aktualisiert die **"lokal"** anzuzeigen (finden Sie unter [anzeigen "lokal"](../../extensibility/debugger/displaying-locals.md) Details).  
  
 Dieses Verfahren dient auch zum Ändern des Werts einer Variablen in der **Überwachen** Fenster, es sei denn ist die `IDebugProperty2` Objekt verknüpft ist, mit dem Wert der lokalen, die anstelle von verwendet wird die `IDebugProperty2` Objekt verknüpft ist, mit der lokalen sich selbst.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Beispielimplementierung der Änderungen von Werten](../../extensibility/debugger/sample-implementation-of-changing-values.md)  
 Im MyCEE-Beispiel verwendet, um den Prozess des Umschaltens Werte zu durchlaufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben Sie eine CLR-Ausdrucksauswertung](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Anzeigen von lokalen Variablen](../../extensibility/debugger/displaying-locals.md)

