---
title: Umgestalten von Python-Code
description: Komfortables Umgestalten von Python-Code in Visual Studio durch Umbenennen von Bezeichnern, Extrahieren von Methoden, Hinzufügen von Imports und Entfernen von nicht verwendeten Imports.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 29a7bec902f28c67e5e6d6e9d63d9a85239c32c1
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586364"
---
# <a name="refactor-python-code"></a>Umgestalten von Python-Code

Visual Studio bietet verschiedene Befehle zum automatischen Transformieren und Bereinigen Ihres Python-Quellcodes:

- [Umbenennen](#rename): Benennt eine ausgewählte Klasse, Methode oder Variable um.
- [Methode extrahieren](#extract-method): Erstellt eine neue Methode aus dem ausgewählten Code.
- [Import hinzufügen](#add-import): Stellt ein Smarttag zum Hinzufügen eines fehlenden Imports bereit.
- [Nicht verwendete Importe entfernen](#remove-unused-imports): Entfernt nicht verwendete Importe.

## <a name="rename"></a>Umbenennen

1. Klicken Sie mit der rechten Maustaste auf den Bezeichner, den Sie umbenennen möchten, und wählen Sie **Umbenennen** aus. Alternativ dazu platzieren Sie den Textcursor in diesem Bezeichner und wählen den Menübefehl (**F2**) **Bearbeiten** > **Umgestalten** > **Umbenennen** aus.
1. Geben Sie in dem **Umbenennen**-Dialogfeld, das geöffnet wird, den neuen Namen für den Bezeichner ein, und wählen Sie **OK**:

  ![Eingabe des neuen Bezeichnernamens](media/code-refactor-rename-1.png)

1. Wählen Sie im nächsten Dialogfeld die Dateien und Instanzen in Ihrem Code aus, auf die die Umbenennung angewendet werden soll. Wählen Sie eine beliebige einzelne Instanz aus, um eine Vorschau der Änderung anzuzeigen:

  ![Dialogfeld zum Auswählen der zu ändernden Elemente](media/code-refactor-rename-2.png)

1. Wählen Sie **Anwenden** aus, um die Änderungen für Ihre Quellcodedateien zu übernehmen. (Diese Aktion kann rückgängig gemacht werden.)

## <a name="extract-method"></a>Methode extrahieren

1. Wählen Sie die Codezeilen oder den Ausdruck aus, die in eine separate Methode extrahiert werden soll(en).
1. Wählen Sie den Menübefehl **Bearbeiten** > **Umgestalten** > **Methode extrahieren** aus, oder drücken Sie die Tasten **STRG**+**R** > **M**.
1. Geben Sie im angezeigten Dialogfeld einen neuen Methodennamen ein, geben Sie an, wo die Methode extrahiert werden soll, und wählen Sie Abschlussvariablen. Nicht zum Abschließen ausgewählte Variablen werden in Methodenargumente umgewandelt:

  ![Dialogfeld „Methode extrahieren“](media/code-refactor-extract-method-1.png)

1. Wählen Sie **OK** aus, und der Code wird entsprechend geändert:

  ![Auswirkungen des Befehls „Methode extrahieren“](media/code-refactor-extract-method-2.png)

## <a name="add-import"></a>Import hinzufügen

Wenn Sie den Textcursor in einem Bezeichner platzieren, der keine Typinformationen enthält, stellt Visual Studio ein Smarttag bereit (das Glühbirnensymbol links neben dem Code), dessen Befehle die erforderliche `import`- oder `from ... import`-Anweisung hinzufügen:

![Smarttag „Import hinzufügen“](media/code-refactor-add-import-1.png)

Visual Studio bietet `import`-Vervollständigungen für Pakete und Module auf oberster Ebene im aktuellen Projekt und der Standardbibliothek. Visual Studio bietet auch `from ... import`-Vervollständigungen für Submodule und Subpakete sowie für Modulmember. Vervollständigungen umfassen Funktionen, Klassen oder exportierte Daten. Durch Auswahl einer Option wird die Anweisung am Anfang der Datei hinter anderen Importvorgängen hinzugefügt. Wenn das gleiche Modul bereits importiert wurde, wird die Anweisung in eine vorhandene `from ... import`-Anweisung eingefügt.

![Hinzufügen eines Imports – Ergebnis](media/code-refactor-add-import-2.png)

Visual Studio versucht, Member herauszufiltern, die nicht tatsächlich in einem Modul definiert sind, wie z.B. Module, die in ein anderes Modul importiert werden, aber keine untergeordneten Elemente des Moduls sind, das den Importvorgang ausführt. Viele Module verwenden z.B. `import sys` statt `from xyz import sys`, daher sehen Sie keinen Abschluss beim Importieren von `sys` aus anderen Modulen, auch wenn in den Modulen ein `__all__`-Member fehlt, der `sys` ausschließt.

Auf ähnliche Weise filtert Visual Studio Funktionen, die aus anderen Modulen oder aus dem integrierten Namespace importiert werden. Wenn ein Modul z.B. die `settrace`-Funktion aus dem `sys`-Modul importiert, könnten Sie die Funktion theoretisch aus diesem Modul importieren. Es empfiehlt sich jedoch, `import settrace from sys` direkt zu verwenden, daher bietet Visual Studio diese Anweisung separat an.

Wenn ein Element normalerweise ausgeschlossen würde, aber andere Werte enthält, die eingeschlossen würden (weil dem Namen z.B. im Modul ein Wert zugewiesen wurde), schließt Visual Studio den Import trotzdem aus. Dieses Verhalten geht davon aus, dass der Wert nicht exportiert werden sollte, weil er in einem anderen Modul definiert wurde und daher die zusätzliche Zuweisung wahrscheinlich einen Pseudowert erzeugt, der ebenfalls nicht exportiert wird.

## <a name="remove-unused-imports"></a>Nicht verwendete Importe entfernen

Beim Schreiben von Code entstehen leicht `import`-Anweisungen für Module, die gar nicht verwendet werden. Visual Studio analysiert Ihren Code und kann daher automatisch ermitteln, ob eine `import`-Anweisung benötigt wird. Dafür prüft Visual Studio, ob der importierte Name in dem Geltungsbereich verwendet wird, in dem die Anweisung auftritt.

Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im Editor, und wählen Sie **Importe entfernen** aus. Sie können aus den Optionen **Alle Geltungsbereiche** oder **Aktueller Geltungsbereich** auswählen:

![Menü zum Entfernen von Importen](media/code-refactor-remove-imports-1.png)

Visual Studio nimmt dann die entsprechenden Änderungen am Code vor:

![Entfernen von Importen – Auswirkungen](media/code-refactor-remove-imports-2.png)

Beachten Sie, dass Visual Studio keine Ablaufsteuerung berücksichtigt – die Verwendung eines Namens vor einer `import`-Anweisung wird genauso verarbeitet, als würde der Name tatsächlich verwendet. Visual Studio ignoriert auch alle `from __future__`-Importe, Importe, die innerhalb einer Klassendefinition ausgeführt werden, sowie Importe aus `from ... import *`-Anweisungen.