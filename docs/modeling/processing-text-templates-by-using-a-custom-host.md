---
title: Verarbeiten von Textvorlagen mithilfe eines benutzerdefinierten Hosts
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 87d9f5f489bffcc624ff758c89e5d3a230a68d01
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859340"
---
# <a name="process-text-templates-by-using-a-custom-host"></a>Verarbeiten von Textvorlagen mithilfe eines benutzerdefinierten Hosts

Die *Textvorlagen-Transformationsprozess* wird eine *Textvorlage* Datei als Eingabe und erzeugt eine Textdatei, die als Ausgabe. Sie können das Texttransformationsmodul aufrufen, aus Visual Studio-Erweiterung oder einer eigenständigen Anwendung, die auf einem Computer auf dem Visual Studio installiert ist. Sie müssen jedoch Bereitstellen einer *Textvorlagenhost*. Diese Klasse verbindet die Vorlage mit der Umgebung. Sie sucht nach Ressourcen wie Assemblys und Includedateien und verarbeitet die Ausgabe und Fehlermeldungen.

> [!TIP]
> Wenn Sie schreiben ein Paket oder eine Erweiterung, die in Visual Studio ausgeführt wird, erwägen Sie, die den Textvorlagendienst, anstatt einen eigenen Host. Weitere Informationen finden Sie unter [Aufrufen von Texttransformation in einer VS-Erweiterung](../modeling/invoking-text-transformation-in-a-vs-extension.md).

> [!NOTE]
> Von der Verwendung von Textvorlagentransformationen in Serveranwendungen wird abgeraten. Textvorlagentransformationen sollten nur in einem einzelnen Thread verwendet werden. Dies liegt daran, dass die Textvorlagen-Engine eine einzelne AppDomain wieder verwendet, um Vorlagen zu übersetzen, zu kompilieren und auszuführen. Der übersetzte Code ist nicht auf Threadsicherheit hin konzipiert. Die Engine soll Dateien seriell verarbeiten, wie in Visual Studio-Projekt zur Entwurfszeit.
>
> Laufzeit-Anwendungen, sollten Sie vorverarbeitete Textvorlagen: finden Sie unter [Run-Time-Textgenerierung mithilfe von T4-Textvorlagen](../modeling/run-time-text-generation-with-t4-text-templates.md).

Wenn in der Anwendung zur Kompilierzeit korrigierte Vorlagen verwendet werden, ist es einfacher, vorverarbeitete Textvorlagen zu verwenden. Sie können diesen Ansatz auch verwenden, wenn Ihre Anwendung auf einem Computer ausgeführt wird, auf dem Visual Studio nicht installiert ist. Weitere Informationen finden Sie unter [Run-Time-Textgenerierung mithilfe von T4-Textvorlagen](../modeling/run-time-text-generation-with-t4-text-templates.md).

## <a name="execute-a-text-template-in-your-application"></a>Führen Sie eine Textvorlage in Ihrer Anwendung

Zum Ausführen einer Textvorlage rufen Sie die ProcessTemplate-Methode von <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> auf:

```csharp
using Microsoft.VisualStudio.TextTemplating;
...
Engine engine = new Engine();
string output = engine.ProcessTemplate(templateString, host);
```

 Die Anwendung muss die Vorlage finden und bereitstellen und die Ausgabe verarbeiten.

 Im `host`-Parameter muss eine Klasse angegeben werden, die <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> implementiert. Diese Methode wird von der Engine aufgerufen.

 Der Host muss in der Lage sein, Fehler zu protokollieren und Verweise auf Assemblys und Includedateien aufzulösen, er muss eine Anwendungsdomäne bereitstellen, in der die Vorlage ausgeführt werden kann, und den entsprechenden Prozessor für jede Anweisung aufrufen.

 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> wird definiert, **Microsoft.VisualStudio.TextTemplating.\*. 0.Dll**, und <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> ist definiert **Microsoft.VisualStudio.TextTemplating.Interfaces.\*. 0.Dll**.

## <a name="in-this-section"></a>In diesem Abschnitt
 [Exemplarische Vorgehensweise: Erstellen eines benutzerdefinierten Textvorlagenhosts](../modeling/walkthrough-creating-a-custom-text-template-host.md) erfahren Sie, wie Erstellung ein benutzerdefinierten Textvorlagenhosts, der die Textvorlagenfunktion außerhalb von Visual Studio zur Verfügung stellt.

## <a name="reference"></a>Referenz
 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>

## <a name="related-sections"></a>Verwandte Abschnitte

- [Das Textvorlagen-Transformationsprozess](../modeling/the-text-template-transformation-process.md) beschreibt die Funktionsweise der TextTransformation und die Teile anpassen kann.
- [Erstellen von benutzerdefinierten T4 Text Vorlage Richtlinie Prozessoren](../modeling/creating-custom-t4-text-template-directive-processors.md) bietet eine Übersicht über Textvorlagen-anweisungsprozessoren für Textvorlagen.