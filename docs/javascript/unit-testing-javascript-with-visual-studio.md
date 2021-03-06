---
title: Unittests in Node.js
description: Visual Studio bietet Unterstützung zum Durchführen von Unittests für JavaScript-Code mithilfe der Node.js-Tools für Visual Studio.
ms.custom: ''
ms.date: 06/06/2018
ms.technology: vs-nodejs
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: bc2a839583f62f3efab18fdb55274ec559d5e6cf
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924790"
---
# <a name="unit-testing-in-nodejs"></a>Unittests in Node.js

Mithilfe der Node.js-Tools für Visual Studio können Sie Komponententests mit gängigen JavaScript-Frameworks schreiben und ausführen, ohne zu einer Eingabeaufforderung wechseln zu müssen.

Folgende Frameworks werden unterstützt:
* Mocha ([mochajs.org](http://mochajs.org/))
* Jasmine ([Jasmine.github.io](https://jasmine.github.io/))
* Tape ([github.com/substack/tape](https://github.com/substack/tape))
* Export Runner (dieses Framework bezieht sich speziell auf Node.js-Tools für Visual Studio)

> [!WARNING]
> Ein Problem in Tape verhindert derzeit die Ausführung von Tape-Tests. Mit der Zusammenführung von [PR 361](https://github.com/substack/tape/pull/361) sollte das Problem behoben sein.

Wenn Ihr bevorzugtes Framework nicht unterstützt wird, finden Sie unter [Add support for a unit test framework (Hinzufügen der Unterstützung für ein Komponententest-Framework)](#addingFramework) Informationen zum Hinzufügen der Unterstützung. 

## <a name="write-unit-tests"></a>Schreiben von Komponententests

Stellen Sie vor dem Hinzufügen von Komponententests zu Ihrem Projekt sicher, dass das Framework, das Sie verwenden möchten, lokal in Ihrem Projekt installiert ist. Mit dem [NPM-Paketinstallationsfenster](npm-package-management.md#npmInstallWindow) lässt sich das ganz einfach bewerkstelligen.

Vorzugsweise sollten Sie Komponententests hinzufügen, indem Sie in Ihrem Projekt einen *Testordner* erstellen und diesen Ordner in den Projekteigenschaften als Teststamm festlegen. Ferner müssen Sie das Testframework auswählen, das Sie verwenden möchten.

![Festlegen von Teststamm und Testframework](../javascript/media/unit-test-project-properties.png)

Über das Dialogfeld **Neues Element hinzufügen** können Sie Ihrem Projekt einfache leere Tests hinzufügen. JavaScript und TypeScript werden in einem Projekt unterstützt.

![Hinzufügen eines neuen Komponententests](../javascript/media/unit-test-add-new-item.png)

Verwenden Sie für einen Mocha-Komponententest folgenden Code:

```javascript
var assert = require('assert');

describe('Test Suite 1', function() {
    it('Test 1', function() {
        assert.ok(true, "This shouldn't fail");
    })

    it('Test 2', function() {
        assert.ok(1 === 1, "This shouldn't fail");
        assert.ok(false, "This should fail");
    })
})
```

Wenn Sie die Komponententestoptionen in den Projekteigenschaften nicht festgelegt haben, müssen Sie sicherstellen, dass für die Eigenschaft **Testframework** im Fenster **Eigenschaften** das richtige Testframework für Ihre Komponententestdateien festgelegt wurde. Dies geschieht automatisch durch die Vorlagen der Komponententestdatei.

![Testframework](../javascript/media/UnitTestsFrameworkMocha.png)

> [!Note]
> Die Komponententestoptionen haben Vorrang vor den Einstellungen für einzelne Dateien.

Nach dem Öffnen des Test-Explorers (wählen Sie **Test** > **Windows** > **Test-Explorer** aus), erkennt Visual Studio Tests und zeigt diese an. Wenn zunächst keine Tests angezeigt werden, erstellen Sie das Projekt neu, um die Liste zu aktualisieren.

![Test-Explorer](../javascript/media/UnitTestsDiscoveryMocha.png)

> [!NOTE]
> Die Optionen `outdir` und `outfile` in *tsconfig.json* können nicht verwendet werden, da der Test-Explorer Komponententests in TypeScript-Dateien nicht findet.

## <a name="run-tests"></a>Tests durchführen

Tests können in Visual Studio 2017 oder über die Befehlszeile ausgeführt werden.

### <a name="run-tests-in-visual-studio-2017"></a>Ausführen von Komponententests in Visual Studio 2017

Sie können die Tests durchführen, indem Sie im Test-Explorer auf den Link **Alle ausführen** klicken. Sie können Tests auch ausführen, indem Sie einen oder mehrere Tests oder Gruppen auswählen, mit der rechten Maustaste darauf klicken und im Kontextmenü die Option **Ausgewählte Tests ausführen** auswählen. Tests werden im Hintergrund ausgeführt, und der Test-Explorer aktualisiert die Ergebnisse automatisch und zeigt diese an. Darüber hinaus können Sie auch ausgewählte Tests debuggen, indem Sie **Ausgewählte Tests debuggen** auswählen.

> [!Warning]
> Das Debuggen von Komponententests mit Node 8 und höher funktioniert derzeit nur bei JavaScript-Testdateien. Bei TypeScript-Testdateien werden die Breakpoints nicht erreicht. Verwenden Sie zur Umgehung dieses Problems das Schlüsselwort `debugger`.

> [!NOTE]
> Die Profilerstellung bei Tests und Code Coverage wird derzeit nicht unterstützt.

### <a name="run-tests-from-the-command-line"></a>Ausführen von Tests über die Befehlszeile

Sie können die Tests über die [Developer-Eingabeaufforderung](/dotnet/framework/tools/developer-command-prompt-for-vs) für Visual Studio 2017 mithilfe des folgenden Befehls ausführen:

```
vstest.console.exe <path to project file>\NodejsConsoleApp23.njsproj /TestAdapterPath:<VisualStudioFolder>\Common7\IDE\Extensions\Microsoft\NodeJsTools\TestAdapter
```

Dieser Befehl erzeugt eine Ausgabe ähnlich der folgenden:

```
Microsoft (R) Test Execution Command Line Tool Version 15.5.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
Processing: NodejsConsoleApp23\NodejsConsoleApp23\UnitTest1.js
  Creating TestCase:NodejsConsoleApp23\NodejsConsoleApp23\UnitTest1.js::Test Suite 1 Test 1::mocha
  Creating TestCase:NodejsConsoleApp23\NodejsConsoleApp23\UnitTest1.js::Test Suite 1 Test 2::mocha
Processing finished for framework of Mocha
Passed   Test Suite 1 Test 1
Standard Output Messages:
 Using default Mocha settings
 1..2
 ok 1 Test Suite 1 Test 1

Failed   Test Suite 1 Test 2
Standard Output Messages:
 not ok 1 Test Suite 1 Test 2
   AssertionError [ERR_ASSERTION]: This should fail
       at Context.<anonymous> (NodejsConsoleApp23\NodejsConsoleApp23\UnitTest1.js:10:16)

Total tests: 2. Passed: 1. Failed: 1. Skipped: 0.
Test Run Failed.
Test execution time: 1.5731 Seconds
```

> [!NOTE]
> Wenn eine Fehlermeldung angezeigt wird, die besagt, dass *vstest.console.exe* nicht gefunden werden kann, prüfen Sie, ob Sie tatsächlich die Developer-Eingabeaufforderung und nicht nur eine gewöhnliche Eingabeaufforderung geöffnet haben. 

## <a name="addingFramework"></a>Hinzufügen der Unterstützung für ein Komponententest-Framework

Sie können die Unterstützung für weitere Testframeworks hinzufügen, indem Sie die Erkennungs- und Ausführungslogik mit JavaScript implementieren. Hierzu fügen Sie einen Ordner mit dem Namen des Testframeworks an folgender Stelle hinzu:

`<VisualStudioFolder>\Common7\IDE\Extensions\Microsoft\NodeJsTools\TestAdapter\TestFrameworks`

Dieser Ordner enthält eine JavaScript-Datei mit demselben Namen, mit der die folgenden beiden Funktionen exportiert werden:

* `find_tests`
* `run_tests`

Ein gutes Beispiel für die Implementierungen von `find_tests` und `run_tests` finden Sie in der Implementierung für das Mocha-Komponententestframework unter:

`<VisualStudioFolder>\Common7\IDE\Extensions\Microsoft\NodeJsTools\TestAdapter\TestFrameworks\mocha\mocha.js`

Verfügbare Testframeworks werden beim Start von Visual Studio ermittelt. Wenn ein Framework hinzugefügt wird, während Visual Studio ausgeführt wird, muss Visual Studio neu gestartet werden, damit das Framework erkannt wird. Wenn Sie an der Implementierung Änderungen vornehmen, müssen Sie jedoch keinen Neustart durchführen.