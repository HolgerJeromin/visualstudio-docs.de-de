---
title: 'CA2207: Statische Felder Inline Typs initialisieren | Microsoft-Dokumentation'
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
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0f90e52ed5d80c9b3e97415e920d7d6f4f0972fc
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "47589588"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207: Statische Felder für Werttyp inline initialisieren
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [CA2207: statische Felder Werttyp Inline initialisieren](https://docs.microsoft.com/visualstudio/code-quality/ca2207-initialize-value-type-static-fields-inline).

|||
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Ein Werttyp deklariert einen expliziten statischen Konstruktor.

## <a name="rule-description"></a>Regelbeschreibung
 Wenn ein Werttyp deklariert wird, durchläuft er standardmäßig initialisiert, wenn alle Felder für Werttyp auf 0 (null) festgelegt werden, und alle Verweistypfelder festgelegt sind `null` (`Nothing` in Visual Basic). Ein expliziter statischer Konstruktor ist nur garantiert vor einem Instanzenkonstruktor ausgeführt werden, oder statische Member des Typs aufgerufen wird. Aus diesem Grund, wenn der Typ erstellt wird, ohne einen Instanzkonstruktor aufrufen, wird der statische Konstruktor Ausführung nicht garantiert.

 Wenn alle statische Daten Inline initialisiert und keine expliziter statischer Konstruktor deklariert ist, fügen die C#- und Visual Basic-Compiler die `beforefieldinit` Flag, um die Definition der MSIL-Klasse. Der Compiler fügen auch einen privaten, statischen Konstruktor mit dem statischen Initialisierungscode hinzu. Diese private statische Konstruktor ist garantiert ausgeführt werden, bevor ein statisches Feld des Typs zugegriffen werden.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Zur Behebung wird ein Verstoß gegen diese Regel alle statische Daten initialisieren, wenn sie deklariert ist, und entfernen den statischen Konstruktor.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie keine Warnung dieser Regel.

## <a name="related-rules"></a>Verwandte Regeln
 [CA1810: Statische Felder von Verweistypen inline initialisieren](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)



