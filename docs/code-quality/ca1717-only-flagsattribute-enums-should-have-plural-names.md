---
title: 'CA1717: Nur FlagsAttribute-Enumerationen sollten Pluralnamen aufweisen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 297f6025cb8ea24ad333f9e6962d8659e78eb8d2
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551872"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: Nur FlagsAttribute-Enumerationen sollten Pluralnamen aufweisen
|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|Kategorie|Microsoft.Naming|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Der Name einer extern sichtbare Enumeration in Pluralform endet und die Enumeration ist nicht mit markiert die <xref:System.FlagsAttribute?displayProperty=fullName> Attribut.

## <a name="rule-description"></a>Regelbeschreibung
 Benennungskonventionen für vorgeben, dass ein Pluralname für eine Enumeration gibt an, dass mehr als einen Wert der Enumeration gleichzeitig angegeben werden kann. Die <xref:System.FlagsAttribute> werden Compiler angewiesen, die Enumeration als Bitfeld behandelt werden soll, der bitweise Vorgänge in der Enumeration ermöglicht.

 Wenn nur ein Wert einer Enumeration zu einem Zeitpunkt angegeben werden kann, sollte der Name der Enumeration Singularform sein. Beispielsweise könnte eine Enumeration, die Tage der Woche definiert, gedacht ist für die Verwendung in einer Anwendung in dem Sie mehrere Tage angeben können. Diese Enumeration müssen den <xref:System.FlagsAttribute> 'Days' aufgerufen werden kann. Eine ähnliche-Enumeration, die nur einen einzelnen Tag angegeben werden kann. das Attribut keine, und möglicherweise 'Day' aufgerufen.

 Durch Benennungskonventionen erhalten Bibliotheken, die auf die Common Language Runtime abzielen, ein einheitliches Erscheinungsbild. Dies reduziert die Zeit, die ist erforderlich, um eine neue Softwarebibliothek erfahren, und zudem wird das Kundenvertrauen, dass die Bibliothek von einer Person entwickelt wurde, die Erfahrung in der Entwicklung von verwaltetem Code hat.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Ändern Sie dem Namen der Enumeration Singularform oder Hinzufügen der <xref:System.FlagsAttribute>.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Es ist sicher eine Warnung von der Regel zu unterdrücken, wenn der Name in die Singularform endet.

## <a name="related-rules"></a>Verwandte Regeln
 [CA1714: Flags-Enumerationen sollten Pluralnamen aufweisen](../code-quality/ca1714-flags-enums-should-have-plural-names.md)

 [CA1027: Enumerationen mit FlagsAttribute markieren](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Enumerationen nicht mit FlagsAttribute markieren](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Siehe auch

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [Enum-Entwurf](/dotnet/standard/design-guidelines/enum)