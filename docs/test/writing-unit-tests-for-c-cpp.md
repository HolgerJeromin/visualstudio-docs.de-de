---
title: Schreiben von Komponententests für C/C++ in Visual Studio
ms.date: 11/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 7838d4435c71fa332711c0ef3794c8bed556827a
ms.sourcegitcommit: 4f82c178b1ac585dcf13b515cc2a9cb547d5f949
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341371"
---
# <a name="write-unit-tests-for-cc-in-visual-studio"></a>Schreiben von Komponententests für C/C++ in Visual Studio

Sie können C++-Komponententests genauso wie in allen anderen Sprachen über das Fenster **Test-Explorer** schreiben und ausführen. Weitere Informationen zur Verwendung des **Test-Explorers** finden Sie unter [Ausführen von Komponententests mit dem Test-Explorer](run-unit-tests-with-test-explorer.md).

> [!NOTE]
> Einige Funktionen wie Live Unit Testing, Tests der programmierten UI und IntelliTest werden für C++ nicht unterstützt.

Visual Studio umfasst diese C++-Testframeworks ohne zusätzliche erforderliche Downloads:

- Microsoft-Komponententest-Framework für C++
- Google Test
- Boost.Test
- CTest

Sie können Ihren eigenen Testadapter sowohl für installierte Frameworks als auch für ein beliebiges anderes Framework zur Verwendung in Visual Studio schreiben. Ein Testadapter kann Komponententests in das Fenster **Test-Explorer** integrieren. Im [Visual Studio Marketplace](https://marketplace.visualstudio.com) sind einige Adapter von Drittanbietern verfügbar. Weitere Informationen finden Sie unter [Installieren von Frameworks für Komponententests von Drittanbietern](install-third-party-unit-test-frameworks.md).

**Visual Studio 2017, Version 15.5**

- Der **Google Test-Adapter** ist als Standardkomponente in der Workload **Desktop Development mit C++** enthalten. Er verfügt über eine Projektvorlage, die Sie über das Kontextmenü **Neues Projekt hinzufügen** auf dem Projektmappenknoten im **Projektmappen-Explorer** zu einer Projektmappe hinzufügen können, sowie Optionen, die Sie über **Extras** > **Optionen** konfigurieren können. Weitere Informationen finden Sie unter [How to: Use Google Test in Visual Studio (Vorgehensweise: Verwenden von Google Test in Visual Studio)](how-to-use-google-test-for-cpp.md).

- **Boost.Test** ist als Standardkomponente in der Workload **Desktop Development mit C++** enthalten. Diese Komponente ist zwar in **Test-Explorer** integriert, jedoch gibt es derzeit noch keine Projektvorlage. Darum müssen Sie sie manuell konfigurieren. Weitere Informationen finden Sie unter [How to: Use Boost.Test in Visual Studio (Vorgehensweise: Verwenden von Boost-Test in Visual Studio)](how-to-use-boost-test-for-cpp.md).

- Die Komponente [CMake Tools für Visual Studio](/cpp/ide/cmake-tools-for-visual-cpp), die Teil der Workload **Desktop Development mit C++** ist, umfasst die Unterstützung von **CTest**. Allerdings ist CTest noch nicht vollständig in den **Test-Explorer** integriert. Weitere Informationen finden Sie unter [How to: Use CTest in Visual Studio (Vorgehensweise: Verwenden von CTest in Visual Studio)](how-to-use-ctest-for-cpp.md).

**Visual Studio 2015 und frühere Versionen**

Sie können die Erweiterungen für den Google Test-Adapter und den Boost.Test-Adapter in Visual Studio Marketplace unter [Testadapter für Boost.Test](https://marketplace.visualstudio.com/items?itemName=VisualCPPTeam.TestAdapterforBoostTest) und [Testadapter für Google Test](https://marketplace.visualstudio.com/items?itemName=VisualCPPTeam.TestAdapterforGoogleTest) herunterladen.

## <a name="basic-test-workflow"></a>Grundlegender Testworkflow

Im folgenden Abschnitt werden die grundlegenden ersten Schritte für C++-Komponententests dargestellt. Die Basiskonfigurationen für die Microsoft- und Google Test-Frameworks sind sehr ähnlich. Für Boost.Test müssen Sie ein Testprojekt manuell erstellen.

### <a name="create-a-test-project"></a>Erstellen eines Testprojekts

Sie definieren Tests für mindestens ein Testprojekt und führen diese aus. Das Testprojekt (bzw. die Testprojekte) muss (bzw. müssen) in derselben Projektmappe gespeichert sein wie der Code, den Sie testen möchten. Klicken Sie mit der rechten Maustaste im **Projektmappen-Explorer** auf den Projektmappenknoten, und wählen Sie anschließend **Hinzufügen** > **Neues Projekt** aus, um ein neues Testprojekt hinzuzufügen. Klicken sie dann im linken Bereich auf **Visual C++ Test** und anschließend auf einen der Projekttypen im mittleren Bereich. In der folgenden Abbildung werden Testprojekte dargestellt, auf die Sie zugreifen können, wenn die Workload **Desktop Development mit C++** installiert ist:

![C++-Testprojekte](media/cpp-new-test-project.png)

### <a name="create-references-to-other-projects-in-the-solution"></a>Erstellen von Verweisen auf andere Projekte in der Projektmappe

Fügen Sie einen Verweis auf das Projekt in Ihrem Testprojekt hinzu, damit der Testcode auf die Funktionen in dem zu testenden Projekt zugreifen kann. Klicken Sie im **Projektmappen-Explorer** zunächst mit der rechten Maustaste auf den Knoten für das Testprojekt, und wählen Sie anschließend **Hinzufügen** > **Verweis** aus. Wählen Sie dann in dem Dialogfeld das Projekt bzw. die Projekte aus, das bzw. die Sie testen möchten.

![Verweis hinzufügen](media/cpp-add-ref-test-project.png)

### <a name="add-include-directives-for-header-files"></a>Hinzufügen von #include-Direktiven für Headerdateien

Fügen Sie als Nächstes in der *CPP*-Datei in Ihrem Komponententest eine `#include`-Direktive für sämtliche Headerdateien hinzu, die die Typen und Funktionen deklarieren, die Sie testen möchten. Geben Sie `#include "` ein, um IntelliSense zu aktivieren, damit es Ihnen bei der Auswahl hilft. Wiederholen Sie diesen Vorgang für alle zusätzlichen Header.

![Hinzufügen von include-Anweisungen](media/cpp-add-includes-test-project.png)

### <a name="write-test-methods"></a>Schreiben von Testmethoden

> [!NOTE]
> In diesem Abschnitt wird die Syntax von Microsoft Unittest-Frameworks für C/C++ dargestellt. Die Dokumentation finden Sie unter: [Microsoft.VisualStudio.TestTools.CppUnitTestFramework API Reference (Referenz für die Microsoft.VisualStudio.TestTools.CppUnitTestFramework-API)](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md). Die Dokumentation zu Google Test finden Sie unter [Google Test Primer (Einführung in Google Test)](https://github.com/google/googletest/blob/master/googletest/docs/primer.md). Die Dokumentation zu Boost.Test finden Sie unter [Boost Test Library: The Unit Test Framework (Boost Test-Bibliothek: Das Framework für Komponententests)](http://www.boost.org/doc/libs/1_46_0/libs/test/doc/html/utf.html).

Die *CPP*-Datei in Ihrem Testprojekt verfügt über eine Stubklasse und -methode, die als Beispiel für das Schreiben von Testcode definiert sind. Beachten Sie, dass die Signaturen die Makros TEST_CLASS und TEST_METHOD verwenden, wodurch Sie die Methoden über das Fenster **Test-Explorer** finden können.

![Hinzufügen von include-Anweisungen](media/cpp-write-test-methods.png)

TEST_CLASS und TEST_METHOD sind Teil des [nativen Microsoft-Testframeworks](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md). Der **Test-Explorer** erkennt Testmethoden in anderen unterstützten Frameworks auf dieselbe Weise.

Das Makro TEST_METHOD gibt „Void“ zurück. Verwenden Sie die statische Methode in der `Assert`-Klasse, um die tatsächlichen Ergebnisse im Vergleich zu den erwarteten Ergebnissen zu vergleichen und um ein Testergebnis zu erzeugen. Im folgenden Beispiel wird angenommen, dass `MyClass` über einen Konstruktor verfügt, der einen `std::string` akzeptiert. Es kann getestet werden, ob der Konstruktor die Klasse wie erwartet initialisiert:

```cpp
        TEST_METHOD(TestClassInit)
        {
            std::string name = "Bill";
            MyClass mc(name);
            Assert::AreEqual(name, mc.GetName());
        }
```
Im vorstehenden Beispiel bestimmt das Ergebnis des Aufrufs `Assert::AreEqual`, ob der Test erfolgreich ausgeführt werden kann oder fehlschlägt. Die Assert-Klasse enthält einige andere Methoden zum Vergleichen der erwarteten Ergebnisse mit den tatsächlichen Ergebnissen.

Sie können der Testmethode *Merkmale* hinzufügen, um Testbesitzer, die Priorität und andere Informationen anzugeben. Sie können diese Werte verwenden, um Tests im **Test-Explorer** zu sortieren und in Gruppen zu unterteilen. Weitere Informationen finden Sie unter [Run unit tests with Test Explorer (Ausführen von Komponententests mit dem Test-Explorer)](run-unit-tests-with-test-explorer.md).

### <a name="run-the-tests"></a>Tests ausführen

1. Klicken Sie im Menü **Test** auf **Windows** > **Test-Explorer**. In der folgenden Abbildung wird ein Testprojekt dargestellt, für das noch keine Tests ausgeführt wurden.

   ![Test-Explorer vor dem Ausführen von Tests](media/cpp-test-explorer.png)

   > [!NOTE]
   > Die CTest-Integration für den **Test-Explorer** ist noch nicht verfügbar. Führen Sie CTest-Tests über das Hauptmenü von CMake aus.

1. Wenn Ihre Tests nicht im Fenster angezeigt werden, erstellen Sie das Testprojekt, indem Sie mit der rechten Maustaste auf dessen Knoten im **Projektmappen-Explorer** klicken und **Erstellen** oder **Neu erstellen** auswählen.

1. Klicken Sie im **Test-Explorer** auf **Alle ausführen**, oder wählen Sie die Tests aus, die Sie ausführen möchten. Klicken Sie für weitere Optionen, einschließlich des Ausführens im Debugmodus mit aktivierten Breakpoints, mit der rechten Maustaste auf einen Test. Wenn alle Tests ausgeführt wurden, wird in dem Fenster dargestellt, welche Tests erfolgreich waren und welche fehlgeschlagen sind:

![Test-Explorer nach dem Ausführen von Tests](media/cpp-test-explorer-passed.png)

Bei fehlgeschlagenen Tests werden in einer Meldung Details angezeigt, die Ihnen dabei helfen sollen, den Grund für das Problem zu finden. Sie können mit der rechten Maustaste erst auf den fehlgeschlagenen Test klicken und dann auf **Ausgewählte Tests debuggen**, um die Funktion, bei der der Fehler aufgetreten ist, genau zu überprüfen.

Weitere Informationen zur Verwendung des **Test-Explorers** finden Sie unter [Ausführen von Komponententests mit dem Test-Explorer](run-unit-tests-with-test-explorer.md).

Bewährte Methoden im Zusammenhang mit Komponententests finden Sie unter [Grundlagen zum Komponententest](unit-test-basics.md).

## <a name="see-also"></a>Siehe auch

[Ausführen von Komponententests für Code](unit-test-your-code.md)
