---
title: 'Gewusst wie: Erzwingen von wartbarem Code mit einer Eincheckrichtlinie für die Codeanalyse'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 402b8e24b68f39524a9095a6ad5b177ab963f05a
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44281038"
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>Gewusst wie: Erzwingen von wartbarem Code mit einer Eincheckrichtlinie für die Analyse

Entwickler können das Codemetrik-Tool verwenden, um die Komplexität und verwaltbarkeit ihres Codes messen, aber die Codemetrik kann nicht als Teil einer Eincheckrichtlinie aufgerufen. Sie können jedoch Aktivieren von Codeanalyseregeln, die die Kompatibilität Ihres Codes mit Code Metriken Standards zu überprüfen und die Regeln durch Check-in-Richtlinien zu erzwingen. Weitere Informationen zu codemetriken finden Sie unter [Code Metrikwerte](../code-quality/code-metrics-values.md).

Sie können die Vererbungstiefe, Klassenkopplung, Wartbarkeitsindex und Komplexitätsregeln zum Erzwingen von wartbarem Code mit einer Eincheckrichtlinie für Codeanalyse aktivieren. Alle vier dieser Regeln werden in der Codeanalyse Gruppenrichtlinienverwaltungs-Editor unter der Kategorie "Wartbarkeitsregeln" gefunden.

Administratoren für Team Foundation-Versionskontrolle können die Anforderungen in der Eincheckrichtlinie für die Verwaltbarkeit von Codeanalyseregeln hinzufügen. Diese checken Sie Richtlinien für Entwickler zum Ausführen der Codeanalyse, die auf Grundlage dieser regeländerungen vor dem Initiieren eines benötigen.

## <a name="to-open-the-code-analysis-policy-editor"></a>Um die Codeanalyserichtlinie-Editor zu öffnen

1. In **Team Explorer**mit der rechten Maustaste auf das Projekt, klicken Sie auf **Projekteinstellungen**, und klicken Sie dann auf **Quellcodeverwaltung**.

     Die **Quellcodeverwaltung** Dialogfeld wird angezeigt.

2. Auf der **Eincheckrichtlinie** Registerkarte, und klicken Sie auf **hinzufügen**.

     Die **Eincheckrichtlinie hinzufügen** Dialogfeld wird angezeigt.

3. In der **Eincheckrichtlinie** Liste der **Codeanalyse** , und klicken Sie dann auf **OK**.

     Die **Code Codeanalyserichtlinien-Editor** Dialogfeld wird angezeigt.

## <a name="to-enable-code-analysis-maintainability-rules"></a>So aktivieren Sie die Verwaltbarkeit von Codeanalyseregeln

1. In der **Code Codeanalyserichtlinien-Editor** Dialogfeld **Regeleinstellungen**, erweitern Sie die **Wartbarkeitsregeln** Knoten.

2. Wählen Sie die Kontrollkästchen für die folgenden Regeln:

    -   Vererbungstiefe: **CA1501 AvoidExcessiveInheritance** -Schwellenwert: Warnung bei mehr als 5 Ebenen

    -   Komplexität: **CA1502 AvoidExcessiveComplexity** -Schwellenwert: Warnung bei mehr als 25

    -   Wartbarkeitsindex: **CA1505 AvoidUnmaintainableCode** -Schwellenwert: Warnung bei weniger als 20

    -   Klassenkopplung: **CA1506 AvoidExcessiveClassCoupling** -Schwellenwert: Warnung bei mehr als 80 für eine Klasse und mehr als 30 für eine Methode

    Wählen Sie außerdem, wenn Sie einen Regelverstoß, um einen erfolgreichen Build zu verhindern möchten, die **behandeln Warnung als Fehler** Kontrollkästchen neben der Beschreibung der Regel.

3. Klicken Sie auf **OK**. Die neue Richtlinie gilt jetzt Eincheckvorgängen.

## <a name="see-also"></a>Siehe auch

- [Codemetrikwerte](../code-quality/code-metrics-values.md)
- [Erstellen und Verwenden von Eincheckrichtlinien für die Analyse](../code-quality/creating-and-using-code-analysis-check-in-policies.md)