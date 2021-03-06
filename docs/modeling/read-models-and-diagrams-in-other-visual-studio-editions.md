---
title: Lesen von Modellen und Diagrammen in anderen Versionen von Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: cfd6188bc4d48f26e85ae8778d75d2fa99ef0f25
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859678"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Lesen von Modellen und Diagrammen in anderen Versionen von Visual Studio
Wenn Sie ein Model in einer Version von Visual Studio öffnen, die keine Modellerstellung unterstützt, wird das Modell im schreibgeschützten Modus geöffnet. In diesem Modus können Sie das Layout der Diagramme ändern, aber nicht das Modell.

 Welche Versionen von Visual Studio die Modellerstellung unterstützen, finden Sie unter [versionsunterstützung für Architektur- und Modellierungstools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="obtaining-access-to-a-model-and-diagrams"></a>Erhalten von Zugriff auf ein Modell und Diagramme
 Um ein Abhängigkeitsdiagramm zu lesen, müssen Sie zunächst Visual Studio verwenden, um das Modellierungsprojekt zu öffnen, und öffnen Sie dann auf das Diagramm in diesem.

 Aus diesem Grund sollten Sie ein Abhängigkeitsdiagramm, lesen müssen Sie auch den Zugriff auf das Modellierungsprojekt in denen es erstellt wurde. Sie erreichen dies durch den Zugriff auf das Projekt aus der quellcodeverwaltung oder eine Kopie der Projektdateien abrufen.

> [!NOTE]
>  Dies gilt nicht für Codezuordnungen und .NET-Klassendiagramme, die aus Code generiert wurden. Diese Diagramme können unabhängig von einem Modellierungsprojekt angezeigt werden.

 Um ein Abhängigkeitsdiagramm zu lesen, lautet der minimale Satz von Dateien, die Sie benötigen:

-   Die beiden Diagrammdateien für das Diagramm, das Sie lesen z. B., möchten **MyDiagram.classdiagram und MyDiagram.classdiagram.layout**.

    > [!NOTE]
    >  Bei Abhängigkeitsdiagramme, sollten Sie auch die Datei mit dem Namen haben _MyDiagram_**. layerdiagram.suppressions**.

-   Die Modellierungsprojektdatei (**MyModel.modelproj**)

-   Die Stammmodelldatei (**ModelDefinition\MyModel. UML**)

-   Die Paketdateien für ein beliebiges Paket im Diagramm auf die verwiesen wird. (**ModelDefinition\MyPackage. UML**)

## <a name="changes-that-you-can-make-in-read-only-mode"></a>Änderungen, die Sie im schreibgeschützten Modus vornehmen können
 Wenn Sie ein Modell und seine Diagramme in einer Version von Visual Studio öffnen, die keine Modellerstellung unterstützt, können Sie das Modell nicht ändern. Das heißt, dass Sie nicht die Elemente und Beziehungen ändern können, die in den Diagrammen oder im Modell-Explorer angezeigt werden. Sie können jedoch einige Änderungen am Layout der Diagramme vornehmen:

-   Anordnen von Formen und Konnektoren im Diagramm.

-   Erweitern und Reduzieren von Formen.

 Sie können diese Änderungen speichern. Wenn Sie Ihre Änderungen für andere Benutzer sichtbar machen möchten, müssen Sie mindestens Senden der aktualisierten **.layout** Dateien.

## <a name="RelatedTopics"></a> Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Abhängigkeitsdiagramme: Referenz](../modeling/layer-diagrams-reference.md)|Ein Ebenendiagramm stellt die Struktur einer vorhandenen oder vorgeschlagenen Architektur dar. Wenn Code geschrieben wird, kann er automatisch anhand eines Ebenendiagramms überprüft werden.|

## <a name="see-also"></a>Siehe auch

- [Erstellen von Modellen für Ihre App](../modeling/create-models-for-your-app.md)