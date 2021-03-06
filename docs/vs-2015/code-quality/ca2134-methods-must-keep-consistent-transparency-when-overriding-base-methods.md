---
title: 'CA2134: Methoden müssen wahren konsistenten Transparenz beim Überschreiben von Basismethoden | Microsoft-Dokumentation'
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
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: df04e5462e2b03c402ce792b390b476b05873036
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589597"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: Methoden müssen beim Überschreiben von Basismethoden eine konsistente Transparenz wahren
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA2134: Methoden müssen konsistenten Transparenz wahren, beim Überschreiben von Basismethoden](https://docs.microsoft.com/visualstudio/code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods).

|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|Kategorie|Microsoft.Security|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Diese Regel wird ausgelöst, wenn eine Methode mit markiert die <xref:System.Security.SecurityCriticalAttribute> überschreibt eine Methode, die transparent oder mit der <xref:System.Security.SecuritySafeCriticalAttribute>. Die Regel wird auch ausgelöst, wenn eine Methode, die transparent oder mit der <xref:System.Security.SecuritySafeCriticalAttribute> überschreibt eine Methode, die mit einem <xref:System.Security.SecurityCriticalAttribute>.

 Die Regel wird angewendet, wenn eine virtuelle Methode überschrieben oder eine Schnittstelle implementiert wird.

## <a name="rule-description"></a>Regelbeschreibung
 Diese Regel wird beim Versuch, ändern Sie den Security Zugriff auf eine Methode, die sich weiter entlang der Vererbungskette ausgelöst. Beispielsweise ist eine virtuelle Methode in einer Basisklasse transparenten oder sicherheitsrelevanten, muss dann die abgeleitete Klasse es mit einer transparenten oder sicherheitsrelevanten-Methode überschreiben. Im Gegensatz dazu ist das virtuelle sicherheitskritisch, muss die abgeleitete Klasse sie mit eine wichtige Methode überschreiben. Das gleiche gilt für die Schnittstellenmethoden implementieren.

 Transparenzregeln werden erzwungen, wenn der Code JIT-Kompilierung statt zur Laufzeit ist, damit, dass die transparenzberechnung keine dynamische Typinformationen. Aus diesem Grund muss das Ergebnis der Berechnung der Transparenz ausschließlich über den statischen Typen wird der JIT-kompiliert, unabhängig vom dynamischen Typ nicht bestimmt werden können.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, ändern Sie die Transparenz der Methode, die eine virtuelle Methode überschreiben oder Implementieren einer Schnittstelle, um die Transparenz des virtuellen oder Schnittstellenmethode entsprechen.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnungen, die von dieser Regel. Verstöße gegen diese Regel führt in einer Laufzeit <xref:System.TypeLoadException> für Assemblys, die Transparenz der Ebene 2 zu verwenden.

## <a name="examples"></a>Beispiele

### <a name="code"></a>Code
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2134.methodsmustoverridewithconsistenttransparency/cs/ca2134 - methodsmustoverridewithconsistenttransparency.cs#1)]

## <a name="see-also"></a>Siehe auch
 [Sicherheitstransparenter Code, Ebene 2](http://msdn.microsoft.com/library/4d05610a-0da6-4f08-acea-d54c9d6143c0)



