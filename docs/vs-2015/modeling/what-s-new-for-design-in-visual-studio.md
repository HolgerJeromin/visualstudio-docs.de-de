---
title: Was&#39;neues beim Entwurf in Visual Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
ms.assetid: 36ab5c17-6dc0-4075-a28e-a0fa49b11260
caps.latest.revision: 34
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: d710d17caaf60cea7b11a1ebd81d91796fdb46d6
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859106"
---
# <a name="whats-new-for-design-in-visual-studio"></a>Neues beim Entwurf in Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [was&#39;neues beim Entwurf in Visual Studio](https://docs.microsoft.com/visualstudio/modeling/what-s-new-for-design-in-visual-studio).

Dieses Release von Visual Studio bietet die folgenden Verbesserungen, sodass Sie Code besser verstehen und entwerfen können.

 **Code Maps und Abhängigkeitsdiagramme**

 Zum Verstehen bestimmter Abhängigkeiten im Code in Visual Studio Enterprise können Sie diese visuell darstellen, indem Sie Codezuordnungen erstellen. Sie können dann diese Beziehungen mithilfe der Zuordnung navigieren, die neben dem Code angezeigt wird. Anhand der Codezuordnungen können Sie außerdem die Position im Code beim Arbeiten oder Debuggen von Code nachverfolgen, sodass Sie beim Analysieren des Codeaufbaus weniger lesen müssen.

 In der RTM-Version haben wir die Kontextmenüs für Codeelemente und Links benutzerfreundlicher gestaltet, indem wir die Befehle hinsichtlich Auswählen, Bearbeiten, Verwalten von Gruppen und Ändern des Layouts des Gruppeninhalts in Abschnitte eingeteilt haben. Beachten Sie außerdem, dass Testprojekte in einem anderen Format als andere Projekte angezeigt werden und die Symbole für Elemente in der Zuordnung passender gestaltet wurden.

 ![Anzeigen der ausgewählten Elemente in einer neuen Code Map](../ide/media/codemapsshowonnewmap.png "CodeMapsShowOnNewMap")

 Zu den weiteren Verbesserungen gehören:

-   **Verbesserte Top-Down-Diagramme**. Für mittlere bis große Visual Studio-Projektmappen können Sie nun ein vereinfachtes Architektur-Menü verwenden, um weitere nützliche Codezuordnungen für Ihre Lösung abzurufen. Die Assemblys der Projektmappe werden nach den Projektmappenordnern gruppiert, dadurch können Sie Sie im Kontext betrachten und die Mühen nutzen, die Sie in die Strukturierung der Lösung gesteckt haben. Ihnen werden sofort Projekt- und Assemblyverweise und anschließend die Linktypen angezeigt. Darüber hinaus werden die Assemblys, die sich außerhalb der Projektmappe befinden, in einer kompakteren Weise gruppiert.

-   **Testprojekte sind unterschiedlich formatiert und können gefiltert werden**. Sie können jetzt einfach und schnell Testprojekte in der Übersicht ermitteln, da sie unterschiedlich formatiert sind. Sie können auch herausgefiltert werden, damit Sie sich auf den Arbeitscode der Anwendung konzentrieren können.

-   **Vereinfachte externe Abhängigkeitslinks**. Abhängigkeitslinks stellen nicht mehr die Vererbung von System.Object, System.ValueType, System.Enum und System.Delegate dar, dadurch lassen sich externe Abhängigkeiten in der Codezuordnung leichter auffinden.

-   **Drilldown-Abhängigkeitslinks berücksichtigen Filter**. Dadurch erhalten Sie ein nützliches, klar strukturiertes Diagramm beim Erweitern, damit Sie die Rolle für einen Abhängigkeitslink besser nachvollziehen können. Das Diagramm ist weniger überladen und berücksichtigt die Linkfilteroptionen, die Sie ausgewählt haben.

-   **Codeelemente werden zu einer Codezuordnung mit Kontext hinzugefügt**. Da Diagramme jetzt mit ihrem Kontext (bis zum Assembly- und Projektmappenordner, den Sie ggf. herausfiltern können), erhalten Sie weitere nützliche Diagramme beim Ziehen und Ablegen von Codeelementen aus dem Projektmappen-Explorer, der Klassenansicht und dem Objektkatalog; oder beim Auswählen von Elementen im Projektmappen-Explorer und beim Auswählen der Option „In Codezuordnung anzeigen“.

-   **Reaktive Codezuordnungen schneller abrufen**. Drag & Drop-Vorgänge erzeugen ein sofortiges Ergebnis, und die Links zwischen Knoten werden wesentlich schneller erstellt, ohne Auswirkungen auf nachfolgende von Benutzern initiierte Vorgänge wie z. B. das Erweitern eines Knotens oder das Anfordern mehr Knoten zu haben. Beim Erstellen von Codezuordnungen ohne die Lösung zu entwickeln, werden nun alle Ausnahmefälle, wie z. B. wenn Assemblys nicht erstellt werden, verarbeitet.

-   **Überspringen Sie das Neuerstellen der Projektmappe.** Bietet eine bessere Leistung beim Erstellen und Bearbeiten von Diagrammen.

-   **odeelementknoten und Gruppen filtern**. Sie können Ihre Zuordnungen schnell basierend auf der Kategorie durch Ein- oder Ausblenden von Codeelementen und durch das Gruppieren von Codeelementen nach Projektmappenordner, Assemblys, Namespaces, Projektordner und Typen organisieren.

-   **Filtern Sie Beziehungen, damit Diagramme leichter zu lesen sind**. Das Filtern von Links gilt jetzt auch für gruppenübergreifende Links, dadurch gestaltet sich die Arbeit mit dem Filterfenster weniger aufwendig als in vorherigen Versionen.

-   **Erstellen Sie Diagrammen aus der Klassenansicht und im Objektbrowser**. Das Ziehen und Ablegen von Dateien und Assemblys in einer neuen oder vorhandenen Zuordnung funktioniert aus den Klassenansicht- und Objektbrowser-Fenstern.

 Finden Sie unter [projektmappenübergreifendes Zuordnen von Abhängigkeiten](../modeling/map-dependencies-across-your-solutions.md).

 **Andere Entwurfs- und modellierungsänderungen ändert sich in dieser Version:**

-   **Ebenendiagramme**. Aktualisieren Sie diese Diagramme mit der Klassenansicht und dem Objektbrowser. Mithilfe von Ebenendiagrammen können Sie die gewünschten Abhängigkeiten für Ihre Software beschreiben, um die Software-Entwicklungsanforderungen zu erfüllen. Halten Sie den Code anhand dieses Aufbaus konsistent, indem Sie Code finden, der diese Einschränkungen nicht erfüllt und zukünftigen Code anhand dieser Baseline zu validieren.

-   **UML-Diagramme**. Es ist nicht mehr möglich, UML-Klassendiagramme und Sequenzdiagramme im Code zu erstellen. Sie können dieses Diagramm jedoch weiterhin mithilfe der neuen UML-Elemente erstellen.

-   **Architektur-Explorer**. Sie können den Architektur-Explorer nicht mehr zum Erstellen von Diagrammen verwenden. Aber Sie können weiterhin den Projektmappen-Explorer verwenden.

##  <a name="VersionSupport"></a> Edition-Unterstützung für Architektur- und Modellierungstools

Visual Studio 2015 ist in mehreren Versionen verfügbar. Nicht alle diese bieten Unterstützung für die Architektur- und Modellierungstools. Die folgende Tabelle zeigt die Verfügbarkeit jedes Tools.

|**Funktion**|**Enterprise**|**Professional**|**Community**|**Express**|
|-----------------|--------------------|----------------------|-------------------|-----------------|
|**Codezuordnungen**|Ja|Unterstützt nur lesen und Filtern von Code Maps, Hinzufügen neuer allgemeiner Knoten und Erstellen eines neuen gerichteten Diagramms aus einer Auswahl aus.|-|-|
|**UML-Klassendiagrammen**|Ja|-|-|-|
|**UML-Sequenzdiagrammen**|Ja|-|-|-|
|**UML-Anwendungsfalldiagramme**|Ja|-|-|-|
|**UML-Aktivitätsdiagramme**|Ja|-|-|-|
|**UML-Komponentendiagrammen**|Ja|-|-|-|
|**Ebenendiagramme**|Ja|-|-|-|
|**Gerichtete Diagramme** (DGML-Diagramme)|Ja|Ja|-|-|
|**Codeklon**|Ja|-|-|-|