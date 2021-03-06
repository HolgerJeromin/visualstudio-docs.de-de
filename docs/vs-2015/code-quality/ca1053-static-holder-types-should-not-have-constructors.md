---
title: 'CA1053: Statische Haltertypen sollten keine Konstruktoren aufweisen | Microsoft-Dokumentation'
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
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: fb4d397a5262245771ffd54aadc08a29c5cfcee8
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589157"
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053: Statische Haltertypen sollten keine Konstruktoren aufweisen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA1053: Statische Haltertypen sollten keine Konstruktoren](https://docs.microsoft.com/visualstudio/code-quality/ca1053-static-holder-types-should-not-have-constructors).

|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Ein öffentlicher oder verschachtelter öffentlicher Typ deklariert nur statische Member und verfügt über einen öffentlichen oder geschützten Standardkonstruktor.

## <a name="rule-description"></a>Regelbeschreibung
 Der Konstruktor ist überflüssig, da zum Aufrufen statischer Member keine Instanz des Typs erforderlich ist. Darüber hinaus, da der Typ keine nicht statische Member, bietet erstellen Sie eine Instanz Zugriff auf Member des Typs keine.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, entfernen Sie den Standardkonstruktor, oder stellen sie private.

> [!NOTE]
>  Einige Compiler erstellen automatisch einen öffentlichen Standardkonstruktor, wenn der Typ keine Konstruktoren definiert ist. Ist dies der Fall bei Ihrem Typ, fügen Sie einen privaten Standardkonstruktor, um die Verletzung zu entfernen.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel. Das Vorhandensein des Konstruktors legt nahe, dass der Typ nicht um einen statischen Typ ist.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen Typ, der gegen diese Regel verstößt. Beachten Sie, dass kein Standardkonstruktor vorhanden, im Quellcode ist. Wenn dieser Code in eine Assembly kompiliert wird, wird der C#-Compiler einen Standardkonstruktor, einfügen, der gegen diese Regel verstoßen wird. Um dies zu korrigieren, deklarieren Sie einen privaten Konstruktor.

 [!code-csharp[FxCop.Design.StaticTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.StaticTypes/cs/FxCop.Design.StaticTypes.cs#1)]



