---
title: 'CA1408: AutoDual ClassInterfaceType nicht verwenden | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DoNotUseAutoDualClassInterfaceType
- CA1408
helpviewer_keywords:
- CA1408
- DoNotUseAutoDualClassInterfaceType
ms.assetid: 60ca5e02-3c51-42dd-942b-4f950eecfa0f
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 45b9e3b9e562b9b3303d170226845a97af2a0d5a
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589266"
---
# <a name="ca1408-do-not-use-autodual-classinterfacetype"></a>CA1408: AutoDual ClassInterfaceType nicht verwenden
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA1408: AutoDual ClassInterfaceType nicht verwenden](https://docs.microsoft.com/visualstudio/code-quality/ca1408-do-not-use-autodual-classinterfacetype).

|||
|-|-|
|TypeName|DoNotUseAutoDualClassInterfaceType|
|CheckId|CA1408|
|Kategorie|Microsoft.Interoperability|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Component Object Model (COM) sichtbarer Typ ist mit markiert die <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> -Attributsatz auf die `AutoDual` Wert <xref:System.Runtime.InteropServices.ClassInterfaceType>.

## <a name="rule-description"></a>Regelbeschreibung
 Typen, die eine duale Schnittstelle verwenden, ermöglichen Clients die Bindung an ein bestimmtes Schnittstellenlayout. Änderungen an einer zukünftigen Version des Layouts des Typs oder eines Basistyps führen zur Aufhebung der Verbindung zu COM-Clients, die eine Bindung zu der Schnittstelle haben. In der Standardeinstellung Wenn die <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> Attribut nicht angegeben wird, eine nur-Dispatch-Schnittstelle wird verwendet.

 Sofern nicht anders markiert ist, werden alle öffentliche nicht generische Typen für COM sichtbar; alle nicht öffentliche und generische Typen sind für COM nicht sichtbar

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, ändern Sie den Wert von der <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> -Attribut auf die `None` Wert <xref:System.Runtime.InteropServices.ClassInterfaceType> und definieren Sie explizit die Schnittstelle.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie eine Warnung dieser Regel nicht, es sei denn, es sicher ist, dass das Layout des Typs und dessen Basistypen in einer zukünftigen Version nicht geändert werden.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt eine Klasse, die gegen die Regel und eine erneute Deklaration der Klasse, um eine explizite Schnittstelle verwenden.

 [!code-csharp[FxCop.Interoperability.AutoDual#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.AutoDual/cs/FxCop.Interoperability.AutoDual.cs#1)]
 [!code-vb[FxCop.Interoperability.AutoDual#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.AutoDual/vb/FxCop.Interoperability.AutoDual.vb#1)]

## <a name="related-rules"></a>Verwandte Regeln
 [CA1403: Typen mit automatischem Layout sollten nicht für COM sichtbar sein](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)

 [CA1412: ComSource-Schnittstellen als IDispatch markieren](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)

## <a name="see-also"></a>Siehe auch
 [Einführung in die Klassenschnittstelle](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024) [Qualifizieren von .NET-Typen für die Interoperation](http://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd) [Interoperation mit nicht verwaltetem Code](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



