---
title: 'CA2230: Params für Variablenargumente verwenden | Microsoft-Dokumentation'
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
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 67788eb84e52e966cbd36311c2f329d5f57331e0
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589139"
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: params für Variablenargumente verwenden
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA2230: Params für Variablenargumente verwenden](https://docs.microsoft.com/visualstudio/code-quality/ca2230-use-params-for-variable-arguments).

|||
|-|-|
|TypeName|UseParamsForVariableArguments|
|CheckId|CA2230|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Ein öffentlicher oder geschützter Typ enthält eine öffentliche oder geschützte Methode, verwendet der `VarArgs` Aufrufkonvention.

## <a name="rule-description"></a>Regelbeschreibung
 Die `VarArgs` -Aufrufkonvention bei bestimmten Methodendefinitionen, die eine Variable Anzahl von Parametern akzeptieren verwendet wird. Eine Methode mit dem `VarArgs` -Aufrufkonvention wird keine Common Language Specification (CLS) kompatibel und kann nicht in verschiedenen Programmiersprachen zugegriffen werden.

 In c# die `VarArgs` -Aufrufkonvention wird so lange verwendet, wenn die Parameterliste einer Methode endet die `__arglist` Schlüsselwort. Visual Basic unterstützt nicht die `VarArgs` Aufrufkonvention und Visual C++ können Sie die Verwendung nur in nicht verwaltetem Code, der die Ellipse verwendet `...` Notation.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel in C# -Code zu beheben, verwenden die [Params](http://msdn.microsoft.com/library/1690815e-b52b-4967-8380-5780aff08012) -Schlüsselwort anstelle von `__arglist`.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt zwei Methoden, die gegen die Regel verstößt und eine, die die Regel erfüllt.

 [!code-csharp[FxCop.Usage.UseParams#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.UseParams/cs/FxCop.Usage.UseParams.cs#1)]

## <a name="see-also"></a>Siehe auch
 <xref:System.Reflection.CallingConventions?displayProperty=fullName> [Sprachenunabhängigkeit und sprachunabhängige Komponenten](http://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)



