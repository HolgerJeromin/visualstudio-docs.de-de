---
title: 'CA1034: Geschachtelte Typen sollten nicht sichtbar sein | Microsoft-Dokumentation'
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
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5edfdca7fe3834160a7120528b56a2770924bf83
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589724"
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: Geschachtelte Typen sollten nicht sichtbar sein
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA1034: geschachtelte Typen sollten nicht sichtbar sein](https://docs.microsoft.com/visualstudio/code-quality/ca1034-nested-types-should-not-be-visible).

|||
|-|-|
|TypeName|NestedTypesShouldNotBeVisible|
|CheckId|CA1034|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Ein extern sichtbarer Typ enthält eine extern sichtbarer Typ-Deklaration. Geschachtelte Enumerationen und geschützte Typen sind von dieser Regel ausgenommen.

## <a name="rule-description"></a>Regelbeschreibung
 Ein geschachtelter Typ ist ein Typ, der innerhalb des Bereichs eines anderen Typs deklariert. Geschachtelte Typen eignen sich für die Kapselung privater Implementierungsdetails des enthaltenden Typs. Bei dieser Verwendungsart sollten geschachtelte Typen nicht extern sichtbar sein.

 Verwenden Sie keine extern sichtbare geschachtelte Typen, für die logische Gruppierung oder so Namenskonflikte zu vermeiden. Verwenden Sie stattdessen Namespaces.

 Geschachtelte Typen enthalten, das Konzept der Member der Barrierefreiheit, die einige Programmierer nicht verstanden werden.

 Geschützte Typen können in Unterklassen und geschachtelte Typen in erweiterte Anpassungsszenarien verwendet werden.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Wenn Sie nicht beabsichtigen, den geschachtelten Typ extern sichtbar sein wird, ändern Sie den Zugriff des Typs. Andernfalls entfernen Sie den geschachtelten Typ von seinem übergeordneten Element. Ist der Zweck der Schachtelung den geschachtelten Typ kategorisiert, verwenden Sie einen Namespace, um die Hierarchie stattdessen zu erstellen.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen Typ, der gegen die Regel verstößt.

 [!code-cpp[FxCop.Design.NestedTypes#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.NestedTypes/cpp/FxCop.Design.NestedTypes.cpp#1)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NestedTypes/cs/FxCop.Design.NestedTypes.cs#1)]
 [!code-vb[FxCop.Design.NestedTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.NestedTypes/vb/FxCop.Design.NestedTypes.vb#1)]



