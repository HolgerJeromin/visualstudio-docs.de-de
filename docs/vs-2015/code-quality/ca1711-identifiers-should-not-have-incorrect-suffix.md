---
title: 'CA1711: Bezeichner sollten kein falsches Suffix aufweisen | Microsoft-Dokumentation'
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
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2b50c3b4cbdbaa82851d23733d04bf3ff5d68af9
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589169"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: Bezeichner sollten kein falsches Suffix aufweisen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA1711: Bezeichner sollten kein falsches Suffix aufweisen](https://docs.microsoft.com/visualstudio/code-quality/ca1711-identifiers-should-not-have-incorrect-suffix).

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|Kategorie|Microsoft.Naming|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Ein Bezeichner weist ein falsches Suffix auf.

## <a name="rule-description"></a>Regelbeschreibung
 Nur die Namen von Typen, die bestimmte Basistypen erweitern oder bestimmte Schnittstellen bzw. Typen implementieren, die von diesen Typen abgeleitet werden, sollten stets mit bestimmten reservierten Suffixen enden. Für andere Typnamen sollten diese reservierten Suffixe nicht verwendet werden.

 In der folgenden Tabelle werden die reservierten Suffixe sowie die Basistypen und die Schnittstellen aufgeführt, denen die Suffixe zugeordnet sind.

|Suffix|Basistyp/Schnittstelle|
|------------|--------------------------|
|Attribut|<xref:System.Attribute?displayProperty=fullName>|
|Auflistung|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|Dictionary|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|EventHandler|Ein Ereignishandlerdelegat.|
|Ausnahme|<xref:System.Exception?displayProperty=fullName>|
|Berechtigung|<xref:System.Security.IPermission?displayProperty=fullName>|
|Warteschlange|<xref:System.Collections.Queue?displayProperty=fullName>|
|Stapel|<xref:System.Collections.Stack?displayProperty=fullName>|
|Stream|<xref:System.IO.Stream?displayProperty=fullName>|

 Darüber hinaus sollten die folgenden Suffixe **nicht** verwendet werden:

-   delegate

-   Enum

-   Impl – Verwenden Sie stattdessen 'Core'.

-   "Ex" oder ein ähnliches Suffix zur Unterscheidung von einer früheren Version desselben Typs

 Durch Benennungskonventionen erhalten Bibliotheken, die auf die Common Language Runtime abzielen, ein einheitliches Erscheinungsbild. Dadurch wird der Lernaufwand für neue Softwarebibliotheken verringert. Zudem wird das Kundenvertrauen dahingehend gestärkt, dass die Bibliothek von einem erfahrenen Entwickler für verwalteten Code erstellt wurde.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Entfernen Sie das Suffix aus dem Typnamen.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel, es sei denn, das Suffix hat eine eindeutige Bedeutung in der Anwendungsdomäne.

## <a name="related-rules"></a>Verwandte Regeln
 [CA1710: Bezeichner sollten ein richtiges Suffix aufweisen](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>Siehe auch
 [Attribute](http://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b) [NIB: Ereignisse und Delegaten](http://msdn.microsoft.com/en-us/d98fd58b-fa4f-4598-8378-addf4355a115)



