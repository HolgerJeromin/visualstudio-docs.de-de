---
title: Analysieren und Modellieren der Architektur
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, exploring code
- Visual Studio Ultimate, visualizing code
- diagrams - modeling
- Visual Studio ALM, modeling
- application, design
- architecture
- code visualization
- application design
- applications, architecture
- code exploration
- Visual Studio ALM, exploring code
- modeling
- application architecture
- application, modeling
- applications, modeling
- architecture [Visual Studio ALM], modeling
- application modeling
- Visual Studio Ultimate, modeling
- architecture [Visual Studio Ultimate], modeling
- application, architecture
- Visual Studio ALM, visualizing code
- applications, designing
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4ab47830d0d6f3c221d08f6869bd8efcbe5b4ff9
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859717"
---
# <a name="analyze-and-model-your-architecture"></a>Analysieren und Modellieren der Architektur

Stellen Sie sicher, dass Ihre app erfüllt architektonische Anforderungen, indem Sie mithilfe von Visual Studio-Architektur und-Modellierungstools zum Entwerfen und modellieren Ihrer app.

* Wenn Sie Visual Studio zum Visualisieren von Codestruktur, -verhalten und -beziehungen verwenden, können Sie vorhandenen Programmcode besser verstehen.

* Informieren Sie Ihr Team für die Benennung von architekturabhängigkeiten müssen.

* Im Rahmen des Entwicklungsprozesses können Sie Modelle unterschiedlichen Detaillierungsgrads während des gesamten Lebenszyklus der Anwendung erstellen.

Finden Sie unter [Szenario: Ändern des Entwurfs mithilfe von Visualisierung und Modellierung](../modeling/scenario-change-your-design-using-visualization-and-modeling.md).

## <a name="to"></a>Beschreibung

|||
|-|-|
|**Visualisieren von Code**:<br /><br /> -Finden Sie unter Organisation und Beziehungen des Codes, indem Sie codezuordnungen erstellen. Sie können Abhängigkeiten zwischen Assemblys, Namespaces, Klassen, Methoden usw. visualisieren.<br />-Finden Sie der Struktur der Klasse und Member für ein bestimmtes Projekt Klassendiagramme aus Code erstellen.<br />-Finden Sie Konflikte zwischen Ihrem Code und dem Entwurf, erstellen Sie Abhängigkeitsdiagramme, um Code zu überprüfen.|-   [Visualisieren von Code](../modeling/visualize-code.md)<br />-   [Arbeiten mit Klassen und anderen Typen (Klassen-Designer)](../ide/working-with-classes-and-other-types-class-designer.md)<br />-   [Video: Verstehen Sie, Entwerfen von Code mit Visual Studio 2015 Code maps](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2015/502)<br />-   [Video: Überprüfen Sie Ihre architekturabhängigkeiten in Echtzeit](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)|
|**Definieren der Architektur**:<br /><br /> – Definieren und Erzwingen von Einschränkungen für Abhängigkeiten zwischen den Komponenten des Codes, indem Sie Abhängigkeitsdiagramme erstellen.|-   [Video: Überprüfen von architekturabhängigkeiten in Visual Studio (Channel 9)](https://channel9.msdn.com/Events/Connect/2016/170)|
|**Überprüfen des Systems anhand der Anforderungen und des beabsichtigten Entwurfs:**<br /><br /> -Überprüfen Sie codeabhängigkeiten mit Abhängigkeitsdiagrammen, die die beabsichtigte Architektur beschreiben und zu verhindern, dass Änderungen, die mit dem Entwurf in Konflikt stehen.|-   [Video: Überprüfen von architekturabhängigkeiten in Visual Studio (Channel 9)](https://channel9.msdn.com/Events/Connect/2016/170)|
|**Anpassen von Modellen und Diagrammen**:<br /><br /> – Erstellen Sie eigene domänenspezifische Sprachen.|-   [Modeling SDK für Visual Studio - domänenspezifische Sprachen](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|
|**Generieren Sie Text mithilfe von T4-Vorlagen**:<br /><br /> – Verwenden Sie Textblöcke und Steuerelementlogik in Vorlagen, um textbasierte Dateien zu generieren.<br /> -T4 Vorlage Build mit MSBuild in Visual Studio enthalten|-   [Codegenerierung und T4-Textvorlagen](../modeling/code-generation-and-t4-text-templates.md)|
|**Freigeben von Modellen und Code Maps mithilfe der Team Foundation-Versionskontrolle**:<br /><br /> -Fügen Sie die Code Maps, Projekte und Abhängigkeitsdiagramme unter Team Foundation-Versionskontrolle, damit diese freigeben zu können.| |

Welche Editionen von Visual Studio die einzelnen Funktionen unterstützen, finden Sie unter [Edition-Unterstützung für Architektur- und Modellierungstools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)

## <a name="types-of-models-and-typical-uses"></a>Typen von Modellen und typische Verwendungen

### <a name="code-maps"></a>Codezuordnungen
Mit Code Maps können Sie die Organisation und die Beziehungen im Code anzeigen.

**Typische Verwendungen:**

-   Überprüfen Sie Programmcode, um sich mit der Struktur, den Abhängigkeiten sowie dem Aktualisieren vertraut zu machen und um die Kosten für vorgeschlagene Änderungen einschätzen zu können.

**Sieh:**

-   [Projektmappenübergreifendes Zuordnen von Abhängigkeiten](../modeling/map-dependencies-across-your-solutions.md)
-   [Verwenden von Code Maps zum Debuggen von Anwendungen](../modeling/use-code-maps-to-debug-your-applications.md)
-   [Ermitteln potenzieller Probleme mithilfe von Code Map-Analyzern](../modeling/find-potential-problems-using-code-map-analyzers.md)

### <a name="dependency-diagram"></a>Abhängigkeitsdiagramm
Abhängigkeitsdiagrammen können Sie die Struktur einer Anwendung als einen Satz von Ebenen oder Blöcken mit expliziten Abhängigkeiten zu definieren. Sie können die Validierung zum Ermitteln von Konflikten zwischen Abhängigkeiten im Code und Abhängigkeiten in einem Abhängigkeitsdiagramm beschrieben ausführen.

**Typische Verwendungen:**

-   Stabilisieren der Struktur der Anwendung anhand zahlreicher Änderungen während der gesamten Lebensdauer.
-   Ermitteln Sie unbeabsichtigte Abhängigkeitskonflikte, bevor Sie Änderungen am Code einchecken.

**Sieh:**

-   [Erstellen von Abhängigkeitsdiagrammen aus dem Code](../modeling/create-layer-diagrams-from-your-code.md)
-   [Abhängigkeitsdiagramme: Referenz](../modeling/layer-diagrams-reference.md)
-   [Überprüfen von Code mit Abhängigkeitsdiagrammen](../modeling/validate-code-with-layer-diagrams.md)

### <a name="domain-specific-language-dsl"></a>Domänenspezifische Sprache (DSL)
Eine DSL ist eine Notation, die für einen bestimmten Zweck entworfen wird. In Visual Studio ist sie normalerweise eine grafische Darstellung.

**Typische Verwendungen:**

-   Generieren oder Konfigurieren von Teilen einer Anwendung. Es ist ein wenig Aufwand erforderlich, um die Notation und die Tools zu entwickeln. Dadurch können Sie jedoch meist eine bessere Anpassung an die Domäne als bei einer UML-Anpassung erreichen.
-   Bei großen Projekten oder bei Produktlinien, bei denen die Investitionen in die Entwicklung DSL und deren Tools sich deshalb lohnen, weil die DSL für mehrere Projekte verwendet werden kann.

**Sieh:**

-   [Modellierungs-SDK für Visual Studio - Domänenspezifische Sprachen](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)

## <a name="where-can-i-get-more-information"></a>Wo kann ich weitere Informationen abrufen?

[Visual Studio Visualization & Modeling Tools-Forum](http://go.microsoft.com/fwlink/?LinkId=184720)

## <a name="see-also"></a>Siehe auch

- [Neuigkeiten](../modeling/what-s-new-for-design-in-visual-studio.md)
- [DevOps und Anwendungslebenszyklus-Verwaltung](http://msdn.microsoft.com/Library/74a1f71d-7f23-4c71-8fd7-89ede614fab6)
