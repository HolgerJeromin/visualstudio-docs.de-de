---
title: 'CA2208: Argumentausnahmen korrekt instanziieren | Microsoft-Dokumentation'
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
- CA2208
- InstantiateArgumentExceptionsCorrectly
helpviewer_keywords:
- InstantiateArgumentExceptionsCorrectly
- CA2208
ms.assetid: e2a48939-d9fa-478c-b2f9-3bdbce07dff7
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ba99cddfe42e1b6699dba4fa665302581aa68cdc
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47590020"
---
# <a name="ca2208-instantiate-argument-exceptions-correctly"></a>CA2208: Argumentausnahmen korrekt instanziieren
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA2208: Argumentausnahmen korrekt instanziieren](https://docs.microsoft.com/visualstudio/code-quality/ca2208-instantiate-argument-exceptions-correctly).

|||
|-|-|
|TypeName|InstantiateArgumentExceptionsCorrectly|
|CheckId|CA2208|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Möglichen Ursachen gehören die folgenden Situationen:

-   Wird aufgerufen, der (parameterlose) Standardkonstruktor eines Ausnahmetyps, der ist, oder [System.ArgumentException] abgeleitet (<!-- TODO: review code entity reference <xref:assetId:///System.ArgumentException?qualifyHint=True&amp;autoUpgrade=True>  -->).

-   Ein falsches Zeichenfolgenargument wird an einen parametrisierten Konstruktor eines Ausnahmetyps übergeben, das ist oder davon abgeleitet [System.ArgumentException.] (<!-- TODO: review code entity reference <xref:assetId:///System.ArgumentException.?qualifyHint=True&amp;autoUpgrade=True>  -->)

## <a name="rule-description"></a>Regelbeschreibung
 Anstelle von Aufrufen des Standardkonstruktors, rufen Sie die Konstruktorüberladung, die eine aussagekräftigere Ausnahmemeldung bereitgestellt werden können. Die Ausnahmemeldung sollten als Ziel den Entwickler und stellen Sie klar die fehlerbedingung und Informationen zum Korrigieren oder die Ausnahme verhindern.

 Die Signaturen der Konstruktoren von mit einem und zwei Zeichenfolgen <xref:System.ArgumentException> und seinen abgeleiteten Typen sind nicht konsistent in Bezug auf die `message` und `paramName` Parameter. Stellen Sie sicher, dass diese Konstruktoren mit den richtigen Argumenten aufgerufen werden. Die Signaturen lauten wie folgt aus:

 <xref:System.ArgumentException>(String `message`)

 <xref:System.ArgumentException>(String `message`, Zeichenfolge `paramName`)

 <xref:System.ArgumentNullException>(String `paramName`)

 <xref:System.ArgumentNullException>(String `paramName`, Zeichenfolge `message`)

 <xref:System.ArgumentOutOfRangeException>(String `paramName`)

 <xref:System.ArgumentOutOfRangeException>(String `paramName`, Zeichenfolge `message`)

 <xref:System.DuplicateWaitObjectException>(String `parameterName`)

 <xref:System.DuplicateWaitObjectException>(String `parameterName`, Zeichenfolge `message`)

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, rufen einen Konstruktor, eine Meldung und/oder einen Parameternamen an, und stellen Sie sicher, dass die Argumente für den Typ des entsprechenden <xref:System.ArgumentException> aufgerufen wird.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Es ist sicher eine Warnung dieser Regel zu unterdrücken, nur, wenn Sie ein parametrisierter Konstruktor mit den richtigen Argumenten aufgerufen wird.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen Konstruktor, der eine Instanz des Typs "ArgumentNullException" nicht ordnungsgemäß instanziiert wird.

 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/cpp/FxCop.Usage.InheritedPublic.cpp#1)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/cs/FxCop.Usage.InheritedPublic.cs#1)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/vb/FxCop.Usage.InstantiateArgumentExceptionsCorrectly.vb#1)]

## <a name="example"></a>Beispiel
 Im folgende Beispiel werden der oben genannten Verstoß korrigiert, durch den Wechsel der Konstruktorargumente.

 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/cpp/FxCop.Usage.InheritedPublic.cpp#2)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/cs/FxCop.Usage.InheritedPublic.cs#2)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.InstantiateArgumentExceptionsCorrectly/vb/FxCop.Usage.InstantiateArgumentExceptionsCorrectly.vb#2)]



