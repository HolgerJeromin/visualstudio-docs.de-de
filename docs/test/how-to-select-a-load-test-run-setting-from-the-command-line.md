---
title: Festlegen von Visual Studio-Laufzeiteinstellungen für Auslastungstests über die Befehlszeile
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, command line
- load tests, run settings, selecting
ms.assetid: 175d1d58-f09a-4449-b132-a29a394a7c8e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 263f8a671897b5f9c8af835f13214139e3abef17
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382476"
---
# <a name="how-to-select-a-load-test-run-setting-to-use-from-the-command-line"></a>Vorgehensweise: Auswählen einer Testlaufeinstellung für Auslastungstests über die Befehlszeile

Ein Auslastungstest kann mehrere *Laufzeiteinstellungen* umfassen. Laufzeiteinstellungen sind Eigenschaften, die die Art der Ausführung eines Auslastungstests beeinflussen. Laufzeiteinstellungen werden nach Kategorien im **Eigenschaftenfenster** strukturiert. Bei der Ausführung eines Auslastungstests wird die Testlaufeinstellung verwendet, die derzeit als aktiv festgelegt ist.

 Wenn der Auslastungstest nur eine Testlaufeinstellung enthält, handelt es sich dabei immer um den aktiven Knoten. Wenn der Auslastungstest mehrere Laufzeiteinstellungsknoten enthält, können Sie in der Befehlszeile den Knoten auswählen, der bei der Ausführung des Auslastungstests verwendet werden soll. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von weiteren Laufzeiteinstellungen zu einem Auslastungstest](../test/how-to-add-additional-run-settings-to-a-load-test.md).

## <a name="to-change-the-run-setting-from-the-command-line"></a>So ändern Sie die Testlaufeinstellung in der Befehlszeile

1.  Wenn Sie in der Befehlszeile andere Laufzeiteinstellungen eingeben möchten, um die Kontextparameterstrategie zu nutzen, verwenden Sie folgenden Befehl:

    `Set Test.UseRunSetting= CorporateStagingWebServer`

2.  Führen Sie den Auslastungstest mithilfe von "mstest" aus:

    `mstest /testcontainer:loadtest1.loadtest`

## <a name="see-also"></a>Siehe auch

- [Konfigurieren der Laufzeiteinstellungen für Auslastungstests](../test/configure-load-test-run-settings.md)
- [Festlegen von Indikatorensätzen und Schwellenwertregeln für Computer in einem Auslastungstest](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Vorgehensweise: Hinzufügen von weiteren Laufzeiteinstellungen zu einem Auslastungstest](../test/how-to-add-additional-run-settings-to-a-load-test.md)
- [Vorgehensweise: Auswählen der aktiven Laufzeiteinstellungen für einen Auslastungstest](../test/how-to-select-the-active-run-setting-for-a-load-test.md)
