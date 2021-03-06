---
title: 'Tutorial: Arbeiten mit Python, Schritt 6: Arbeiten mit Git'
description: Dies ist Schritt 6 einer grundlegenden Einführung in die Arbeit mit Python in Visual Studio, in dem die Git-bezogenen Features von Visual Studio erläutert werden.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: e0eae43e894b521cc9633df3d6e0c84e8dbb0b20
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "39511326"
---
# <a name="step-6-work-with-git"></a>Schritt 6: Arbeiten mit Git

**Vorheriger Schritt: [Installieren von Paketen und Verwalten Ihrer Python-Umgebung](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)**

Visual Studio bietet die direkte Integration mit lokalen Git-Repositorys und Remote-Git-Repositorys in Diensten wie GitHub und Visual Studio Team Services. Die Integration umfasst das Klonen eines Repositorys, das Übernehmen von Änderungen und das Verwalten von Branches.

In diesem Artikel erhalten Sie einen allgemeinen Überblick über das Erstellen lokaler Git-Repositorys für ein vorhandenes Projekt und über einige Visual Studio-Features, die mit Git in Verbindung stehen.

1. Klicken Sie mit der rechten Maustaste auf die Projektmappe, und klicken Sie dann auf **Projektmappe zur Quellcodeverwaltung hinzufügen**, wenn ein Projekt (z.B. das Projekt aus dem [vorherigen Schritt](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)) in Visual Studio geöffnet ist. Visual Studio erstelle ein lokales Git-Repository, das Ihren Projektcode enthält.

1. Wenn Visual Studio erkennt, dass ein Projekt in einem Git-Repository verwaltet wird, erscheinen am unteren rechten Rand des Visual Studio-Fensters Steuerelemente, die auf Git bezogen sind. Die Steuerelemente zeigen ausstehende Commits, Änderungen, den Namen des Repositorys und den Branch an. Zeigen Sie auf die Steuerelemente, um zusätzliche Informationen anzuzeigen.

    ![Zusätzliche Informationen, die angezeigt werden, wenn auf ein Git-Steuerelement im Visual Studio-Fenster gezeigt wird](media/working-with-git-01.png)

1. Wenn Sie ein neues Repository erstellen oder eines der Git-Steuerelemente auswählen, öffnet Visual Studio den **Team Explorer**. (Sie können das Fenster auch jederzeit über **Ansicht** > **Team Explorer** öffnen.) Das Fenster besteht aus drei Hauptbereichen, zwischen denen Sie über das Dropdownmenü im Header **Team Explorer** wechseln können. Der **Synchronisierungsbereich**, der Veröffentlichungsvorgänge bereitstellt, wird auch angezeigt, wenn Sie das Steuerelement **Push** auswählen (der Pfeil nach oben):

    ![Team Explorer in Visual Studio, nachdem ein lokales Repository erstellt wurde](media/working-with-git-02.png)

1. Klicken Sie auf **Änderungen** (oder auf das Git-Steuerelement mit dem Bleistiftsymbol), um nicht gespeicherte Änderungen zu überprüfen und diese bei Bedarf zu übernehmen.

    ![Team Explorer in Visual Studio, der nicht gespeicherte Änderungen anzeigt](media/working-with-git-03.png)

    Doppelklicken Sie auf eine Datei unter **Änderungen**, um eine Vergleichsansicht für diese zu öffnen:

    ![Vergleichsansicht zu Änderungen an einer Datei](media/working-with-git-05.png)

1. Klicken Sie auf **Branches** (oder das Git-Steuerelement mit einem Branchnamen), um Branches zu untersuchen und Zusammenführungs- und Rebasevorgänge auszuführen:

    ![Team Explorer in Visual Studio, der Branches anzeigt](media/working-with-git-04.png)

1. Wenn Sie auf das Git-Steuerelement mit dem Repositorynamen klicken (**CosineWave** im oben stehenden Bild), zeigt der **Team Explorer** eine **Connect**-Schnittstelle (Verbinden) an, mit der Sie schnell zu einem anderen Repository wechseln können.

1. Wenn Sie ein lokales Repository verwenden, werden gespeicherte Änderungen direkt an das Repository übertragen. Wenn Sie mit einem Remoterepository verbunden sind, klicken Sie auf den Dropdownheader im **Team Explorer** und anschließend auf **Sync**, um zum Abschnitt **Synchronisierung** zu wechseln und mit den dort aufgeführten **Pull**- und **Fetch**-Befehlen zu arbeiten.

## <a name="go-deeper"></a>Ausführlichere Informationen

Eine kurze exemplarische Vorgehensweise für das Erstellen eines Projekts über ein Git-Remoterepository finden Sie unter [Quickstart: Clone a repository of Python code in Visual Studio (Schnellstart: Klonen eines Repositorys mit Python-Code in Visual Studio)](quickstart-03-python-in-visual-studio-project-from-repository.md).

Ein ausführlicheres Tutorial finden Sie unter [Get Started with Git and VSTS (Einstieg in Git und VSTS)](/vsts/git/gitquickstart?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json&view=vsts&tabs=visual-studio). Dort lernen Sie das Behandeln von Mergekonflikten, das Prüfen von Code mit Pull Requests, das Ausführen von Rebasevorgängen und Cherrypicking von Änderungen zwischen Branches kennen.

## <a name="tutorial-review"></a>Review des Tutorials

Glückwunsch zum Abschluss dieses Tutorials zu Python in Visual Studio. In diesem Tutorial haben Sie Folgendes gelernt:

- Erstellen von Projekten und Anzeigen der Projektinhalte
- Verwenden des Code-Editors und Ausführen eines Projekts
- Verwenden Sie das **interaktive** Fenster, um neuen Code zu entwickeln und diesen einfach in den Editor zu kopieren.
- Führen Sie ein abgeschlossenes Programm im Visual Studio-Debugger aus.
- Installieren von Paketen und Verwalten von Python-Umgebungen
- Arbeiten mit Code in einem Git-Repository

Sehen Sie sich für weitere Informationen die folgenden Artikel zu Konzepten und die folgenden Leitfäden an:

- [Erstellen einer C++-Erweiterung für Python](working-with-c-cpp-python-in-visual-studio.md)
- [Veröffentlichen in Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md)
- [Profilerstellung](profiling-python-code-in-visual-studio.md)
- [Komponententests](unit-testing-python-in-visual-studio.md)
