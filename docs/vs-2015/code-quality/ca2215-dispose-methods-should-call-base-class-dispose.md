---
title: 'CA2215: Dispose-Methoden sollten Dispose der Basisklasse aufrufen | Microsoft-Dokumentation'
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
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: bacd16fa8c58fcbe6646e1b7c5f2a26fad8e4ce3
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589151"
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215: Dispose-Methoden müssen die Dispose-Funktion der Basisklasse aufrufen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA2215: Dispose-Methoden sollten Dispose der Basisklasse aufrufen](https://docs.microsoft.com/visualstudio/code-quality/ca2215-dispose-methods-should-call-base-class-dispose).

|||
|-|-|
|TypeName|DisposeMethodsShouldCallBaseClassDispose|
|CheckId|CA2215|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Ein Typ, der implementiert <xref:System.IDisposable?displayProperty=fullName> erbt von einem Typ, der auch implementiert <xref:System.IDisposable>. Die <xref:System.IDisposable.Dispose%2A> Methode der erbende Typ ruft nicht die <xref:System.IDisposable.Dispose%2A> Methode des übergeordneten Typs.

## <a name="rule-description"></a>Regelbeschreibung
 Wenn ein Typ von einem verwerfbaren Typ erbt, muss er Aufrufen der <xref:System.IDisposable.Dispose%2A> Methode des Basistyps von in eine eigene <xref:System.IDisposable.Dispose%2A> Methode. Aufrufen der Methode des Basistyps wird Dispose alle Ressourcen, die von den Basistyp erstellt freigegeben werden.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, rufen `base`.<xref:System.IDisposable.Dispose%2A> in Ihrer <xref:System.IDisposable.Dispose%2A> Methode.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Es ist sicher, um eine Warnung dieser Regel zu unterdrücken, falls der Aufruf von `base`.<xref:System.IDisposable.Dispose%2A> Tritt auf, auf einer tieferen aufrufenden Ebene als die Regel überprüft.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt ein `TypeA` implementiert <xref:System.IDisposable>.

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposablePattern/cs/FxCop.Usage.IDisposablePattern.cs#1)]

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen Typ `TypeB` , die von Typ erbt `TypeA` und ordnungsgemäß ruft seine <xref:System.IDisposable.Dispose%2A> Methode.

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposableBaseCalled/vb/FxCop.Usage.IDisposableBaseCalled.vb#1)]

## <a name="see-also"></a>Siehe auch
 <xref:System.IDisposable?displayProperty=fullName> [Dispose-Muster](http://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)



