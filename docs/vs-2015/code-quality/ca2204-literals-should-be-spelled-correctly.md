---
title: 'CA2204: Literale sollten richtig geschrieben werden | Microsoft-Dokumentation'
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
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 39d841fbfa9be3e3ee5764e986a9688ca4113caf
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589781"
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204: Literale sollten eine korrekte Rechtschreibung aufweisen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA2204: Literale sollten richtig geschrieben werden](https://docs.microsoft.com/visualstudio/code-quality/ca2204-literals-should-be-spelled-correctly).

|||
|-|-|
|TypeName|LiteralsShouldBeSpelledCorrectly|
|CheckId|CA2204|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Eine Methode übergibt eine, die Literalzeichenfolge mit verwendet wird, in einem Parameter oder die Eigenschaft, die eine lokalisierte Zeichenfolge und das Zeichenfolgenliteral erfordert enthält eine oder mehrere Wörter, die von der Rechtschreibprüfung aus der Microsoft-Bibliothek nicht erkannt werden.

## <a name="rule-description"></a>Regelbeschreibung
 Diese Regel prüft eine Literalzeichenfolge, die als Wert übergeben wird, auf einen Parameter oder eine Eigenschaft, wenn eine oder mehrere der folgenden Fälle zutreffen:

-   Die <xref:System.ComponentModel.LocalizableAttribute> Attribut des Parameters oder der Eigenschaft wird festgelegt auf "true".

-   Der Parameter oder die Eigenschaft Name enthält "Text", "Message" oder "Beschriftung".

-   Der Name des Parameters, der auf eine Console.Write "oder" Console.WriteLine-Methode übergeben wird, ist "Value" oder "format".

 Diese Regel analysiert die Literalzeichenfolge in Wörter, die mit Token versehen zusammengesetzte Wörter und überprüft die Rechtschreibung eines einzelnen Worts/Tokens. Informationen zu den Analysealgorithmus, finden Sie unter [CA1704: Bezeichner sollten korrekt geschrieben werden](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

 Standardmäßig wird die Englisch (En) Version der Rechtschreibprüfung verwendet.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, korrigieren Sie die Schreibweise des Worts, oder fügen Sie es zu einem Benutzerwörterbuch. Weitere Informationen zur Verwendung von benutzerdefinierten Wörterbüchern finden Sie unter [wie: Anpassen des Codeanalysewörterbuchs](../code-quality/how-to-customize-the-code-analysis-dictionary.md).

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel. Ordnungsgemäß zu geschriebene Wörter der Lernaufwand für neue Softwarebibliotheken reduzieren.

## <a name="related-rules"></a>Verwandte Regeln
 [CA1704: Bezeichner sollten korrekt geschrieben werden](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)

 [CA1703: Ressourcenzeichenfolgen sollten korrekt geschrieben werden](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)



