---
title: 'CA1415: P-Invokes für korrekt deklarieren | Microsoft-Dokumentation'
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
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c80a68d19e03f7e4b04dae728dd2e9cc120eb370
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589145"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415: P/Invokes korrekt deklarieren
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA1415: deklarieren, P-Invokes korrekt](https://docs.microsoft.com/visualstudio/code-quality/ca1415-declare-p-invokes-correctly).

|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|Kategorie|Microsoft.Interoperability|
|Unterbrechende Änderung|Nicht unterbrechend – Wenn der P/Invoke, die den Parameter deklariert, kann nicht außerhalb der Assembly angezeigt werden. Unterbrechend – Wenn der P/Invoke, die den Parameter deklariert, die außerhalb der Assembly angezeigt werden können.|

## <a name="cause"></a>Ursache
 Eine Plattformaufrufmethode wurde falsch deklariert.

## <a name="rule-description"></a>Regelbeschreibung
 Eine Plattformaufrufmethode greift auf nicht verwalteten Code und ist definiert, mit der `Declare` -Schlüsselwort in [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] oder <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. Derzeit diese Regel sucht Plattformaufrufdeklarationen Methode, die Win32-Funktionen als Ziel, die einen Zeiger auf einen OVERLAPPED-Strukturparameter haben und es ist nicht des zugehörigen verwalteten Parameters ein Zeiger auf eine <xref:System.Threading.NativeOverlapped?displayProperty=fullName> Struktur.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, deklarieren Sie ordnungsgemäß die Plattform invoke-Methode.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt Plattformaufrufmethoden, die die Regel verletzen, und die Regel zu erfüllen.

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DeclarePInvokes/cs/FxCop.Interoperability.DeclarePInvokes.cs#1)]

## <a name="see-also"></a>Siehe auch
 [Interoperabilität mit nicht verwaltetem Code](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



