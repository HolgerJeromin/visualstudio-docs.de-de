---
title: 'CA1008: Enumerationen müssen einen Wert von 0 (null) aufweisen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 60c5e6e93c8ededc7d08d3b917f8066148f133f7
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551794"
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: Enumerationen müssen einen Wert von 0 (null) aufweisen

|||
|-|-|
|TypeName|EnumsShouldHaveZeroValue|
|CheckId|CA1008|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Nicht unterbrechend – Wenn Sie aufgefordert werden, Hinzufügen einer **keine** Wert, der eine nicht-Flagenumeration. Wichtige – Wenn Sie aufgefordert werden, umbenennen oder entfernen alle Enumerationswerte.|

## <a name="cause"></a>Ursache

Eine Enumeration ohne eine angewendeten <xref:System.FlagsAttribute?displayProperty=fullName> definiert sich nicht auf einen Member mit dem Wert 0 (null); oder eine Enumeration, die eine angewendet wurde <xref:System.FlagsAttribute> definiert ein Element mit dem Wert 0 (null), aber der Name ist nicht 'None' oder die Enumeration definiert mehrere NULL-Werten Elemente.

## <a name="rule-description"></a>Regelbeschreibung

Der Standardwert einer nicht initialisierten Enumeration ist, genau wie anderer Werttypen ist 0 (null). Eine Enumeration ohne Flags-Attribut sollten Mitglied definieren, mit dem Wert 0 (null), damit der Standardwert ein gültiger Wert der Enumeration ist. Bei Bedarf, nennen Sie das Element 'None'. Ordnen Sie andernfalls 0 (null), auf den am häufigsten verwendeten Member. Wenn der Wert des ersten Elements der Enumeration nicht in der Deklaration festgelegt ist, ist der Wert in der Standardeinstellung 0 (null).

Wenn eine Enumeration, die die <xref:System.FlagsAttribute> angewendet definiert den Member NULL-Wert, der Name muss 'None', um anzugeben, dass in der Enumeration keine Werte festgelegt wurden. Verwenden einen NULL-Member, für andere Zwecke im Gegensatz zum Ergebnis der Verwendung von ist das <xref:System.FlagsAttribute> , AND und bitweise Operatoren sind nutzlos, mit dem Element. Dies bedeutet, dass nur ein Member den Wert 0 (null) zugewiesen werden soll. Wenn mehrere Elemente, die den Wert 0 (null) haben in einer Enumeration Flags-Attribut auftreten `Enum.ToString()` gibt falsche Ergebnisse für Elemente, die nicht 0 (null) zurück.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen

Definieren Sie einen Member mit dem Wert 0 (null), um einen Verstoß gegen diese Regel für nicht-Enumerationen zu beheben. Dies ist eine nicht unterbrechende Änderung. Namen Sie für Enumerationen, die einen 0 (null) Member definieren dieses Element den "None", und löschen Sie anderer Elemente, die den Wert 0 (null) aufweisen; Dies ist eine unterbrechende Änderung.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken

Unterdrücken Sie keine Warnung dieser Regel, mit Ausnahme von Enumerationen, die zuvor veröffentlicht haben.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt zwei Enumerationen, die die Regel erfüllen und eine Enumeration, `BadTraceOptions`, die gegen die Regel verstößt.

[!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
[!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
[!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]

## <a name="related-rules"></a>Verwandte Regeln

- [CA2217: Enumerationen nicht mit FlagsAttribute markieren](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700: Enumerationswerte nicht mit "Reserviert" benennen](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA1712: Keine Typnamen als Präfixe für Enumerationswerte verwenden](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)
- [CA1028: Der Enumerationsspeicher sollte Int32 sein.](../code-quality/ca1028-enum-storage-should-be-int32.md)
- [CA1027: Enumerationen mit FlagsAttribute markieren](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Siehe auch

- <xref:System.Enum?displayProperty=fullName>