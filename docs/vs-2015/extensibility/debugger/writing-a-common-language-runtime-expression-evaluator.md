---
title: Schreiben eine Common Language Runtime-Ausdrucksauswertung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- expression evaluators, tutorial
- expression evaluation, samples
- debugging [Debugging SDK], expression evaluators tutorial
ms.assetid: bd79d57f-8e0a-4e14-a417-0b1de28fa1b2
caps.latest.revision: 24
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6917a4ad5936792e309b5b14abbc862ca6bd5654
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47521189"
---
# <a name="writing-a-common-language-runtime-expression-evaluator"></a>Schreiben einer Ausdrucksauswertung für die Common Language Runtime
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [schreiben eine Common Language Runtime-Ausdrucksauswertung](https://docs.microsoft.com/visualstudio/extensibility/debugger/writing-a-common-language-runtime-expression-evaluator).  
  
> [!IMPORTANT]
>  In Visual Studio 2015 ist diese Art der Implementierung von ausdrucksauswertungen veraltet. Informationen zu CLR-ausdrucksauswertungen implementieren, finden Sie unter [CLR Ausdrucksauswertungen](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) und [Managed Expression Evaluator Sample](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Die ausdrucksauswertung (EE) ist der Teil einer Debug-Engine (DE), die behandelt die Syntax und Semantik der Programmiersprache, die der gerade gedebuggten Code erstellt. Ausdrücke müssen innerhalb des Kontexts einer Programmiersprache ausgewertet werden. In einigen Sprachen können beispielsweise der Ausdruck "A + B" bedeutet "die Summe von A und b." In anderen Sprachen kann der gleiche Ausdruck "A oder b" bedeuten. Daher muss ein separates EE für jede Programmiersprache geschrieben werden, die zu debuggende Objektcode in Visual Studio-IDE generiert.  
  
 Einige Aspekte der Visual Studio-Paket debuggen, müssen den Code im Kontext der Programmiersprache interpretiert. Z. B. wenn die Ausführung angehalten wird an einem Haltepunkt any-Ausdrücke, die in der Benutzer eingegeben hat eine **Watch** Fenster ausgewertet und angezeigt werden muss. Darüber hinaus kann der Benutzer den Wert einer lokalen Variablen ändern, durch Eingabe eines Ausdrucks in einer **Watch** Fenster oder in der **direkt** Fenster.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Common Language Runtime und Ausdrucksauswertung](../../extensibility/debugger/common-language-runtime-and-expression-evaluation.md)  
 Erklärt, dass beim Integrieren von proprietären Programmiersprache in Visual Studio-IDE, schreiben eine EE Auswerten von Ausdrücken innerhalb des Kontexts der proprietäre Sprache kann in einer Microsoft intermediate Language (MSIL) kompiliert wird, Sie können ohne das Schreiben einer Debug-Engine.  
  
 [Architektur der Ausdrucksauswertung](../../extensibility/debugger/expression-evaluator-architecture.md)  
 Erläutert, wie die erforderlichen EE-Schnittstellen zu implementieren, und rufen Sie die common Language Runtime-Symbol-Dienstanbieter (SP) und den Binder-Schnittstellen.  
  
 [Registrieren einer Ausdrucksauswertung](../../extensibility/debugger/registering-an-expression-evaluator.md)  
 Anmerkungen dieser, dass die EE selbst als eine Klassenfactory mit der common Language Runtime und die Visual Studio-Laufzeitumgebungen registrieren muss.  
  
 [Implementieren einer Ausdrucksauswertung](../../extensibility/debugger/implementing-an-expression-evaluator.md)  
 Beschreibt, wie der Prozess der Auswertung eines Ausdrucks für die Debug-Engine (DE), die Symbol-Dienstanbieter (SP), das binderobjekt und die ausdrucksauswertung (EE) enthält.  
  
 [Anzeigen von lokalen Variablen](../../extensibility/debugger/displaying-locals.md)  
 Beschreibt, wie, wenn die Ausführung angehalten wird, das debugpaket die DE zum Abrufen einer Liste von lokalen Variablen und Argumenten aufruft.  
  
 [Auswerten eines Überwachungsfensterausdrucks](../../extensibility/debugger/evaluating-a-watch-window-expression.md)  
 Beschreibt, wie der Visual Studio-Paket Debuggen die DE zum Bestimmen des aktuellen Werts des jeder Ausdruck in der Liste sehen Sie sich aufruft.  
  
 [Ändern des Werts eines lokalen Elements](../../extensibility/debugger/changing-the-value-of-a-local.md)  
 Erklärt, dass in den Wert eines lokalen Elements ändern, jede Zeile des Fensters "lokal" ein zugeordnetes Objekt verfügt, das die Namen, Typ und aktuellen Wert eines lokalen Elements bereitstellt.  
  
 [Implementieren von Typschnellansichten und benutzerdefinierten Viewern](../../extensibility/debugger/implementing-type-visualizers-and-custom-viewers.md)  
 Erklärt, welche Schnittstelle muss von der Komponente zur Unterstützung von typschnellansichten und benutzerdefinierten Viewern implementiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Studio Debugger-Erweiterbarkeit](../../extensibility/debugger/visual-studio-debugger-extensibility.md)

