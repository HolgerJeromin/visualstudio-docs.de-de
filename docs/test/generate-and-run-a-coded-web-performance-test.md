---
title: Codierte Webleistungstests in Visual Studio
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, walkthroughs
- Web performance tests, creating
- code, Web performance tests
- Web performance tests, coded
ms.assetid: 169e48f9-52fd-4d0b-83d9-54913bde506b
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 663b2e18eb71cb627bd521df0de6bc21c95cef05
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44320748"
---
# <a name="generate-and-run-a-coded-web-performance-test"></a>Generieren und Ausführen eines codierten Webleistungstests

Webleistungstests werden aufgezeichnet, indem die Web-App durchsucht wird. Die Tests sind in Auslastungstests enthalten, um die Leistung der Webanwendung unter der Last mehrerer Benutzer zu messen. Ein Webleistungstest kann in ein codebasiertes Skript konvertiert werden, das Sie wie jeden anderen Quellcode bearbeiten und anpassen können. Beispielsweise können Sie Schleifen- und Verzweigungskonstrukte hinzufügen.

## <a name="generate-a-coded-web-performance-test"></a>Einen codierten Webleistungstest generieren

1.  Wenn Sie keinen Webleistungstest erstellt haben, finden Sie weitere Informationen unter [Record a web performance test (Aufzeichnen eines Webleistungstests)](/azure/devops/test/load-test/run-performance-tests-app-before-release#create-a-web-performance-and-load-test-project?view=vsts).

2.  Generieren Sie den codierten Test.

     ![Einen codierten Webleistungstest generieren](../test/media/web_test_coded_generate.png)

3.  Geben Sie dem Test einen Namen.

     ![Einen Namen für den codierten Webleistungstest eingeben](../test/media/web_test_coded_generate_nametest.png)

     Der neue codierte Test wird im Code-Editor geöffnet.

     In Abhängigkeit davon, welche Webleistungs- und Auslastungstest-Projektvorlage Sie zu Ihrer Projektmappe hinzugefügt haben, wird der Code entweder in Visual Basic oder Visual C# generiert.

     ![Der neue codierte Test wird im Code-Editor geöffnet](../test/media/web_test_coded_generate_opencodeeditor.png)

     Im Code können Sie sehen, dass die GetRequestEnumerator()-Methode in C# bzw. die Run()-Methode in Visual Basic jede Validierungsregel und jede Webanforderung enthält, die im umcodierten Test enthalten war.

4.  Um zu demonstrieren, wie einfacher Code hinzugefügt wird, führen Sie einen Bildlauf zum Ende der Methode durch, und fügen Sie nach dem Code für die letzte Webanforderung folgenden Code hinzu:

    ```c#
    if (DateTime.Today.DayOfWeek == DayOfWeek.Wednesday)
    {
        WebTestRequest customRequest = new WebTestRequest("http://weather.msn.com/");
        yield return customRequest;
    }
    else
    {
        WebTestRequest customRequest = new WebTestRequest("http://msdn.microsoft.com/");
        yield return customRequest;
    }
    ```

    ```vb
    If DateTime.Today.DayOfWeek = DayOfWeek.Wednesday Then
        Dim customRequest As WebTestRequest = New WebTestRequest("http://weather.msn.com/")
        MyBase.Send(customRequest)
    Else
        Dim customRequest As WebTestRequest = New WebTestRequest("http://msdn.microsoft.com/")
        MyBase.Send(customRequest)
    End If
    ```

5.  Erstellen Sie die Projektmappe, um sicherzustellen, dass der benutzerdefinierte Code kompiliert werden kann.

6.  Führen Sie den Test aus.

     ![Ausführung des codierten Webleistungstests](../test/media/web_test_coded_generate_run.png)

     Und da der Tag, am dem dies ausgeführt wurde, ein Mittwoch war...

     ![Ergebnisse des codierten Webleistungstests](../test/media/web_test_coded_generate_results.png)

## <a name="qa"></a>Fragen und Antworten

### <a name="q-can-i-run-more-than-one-test-at-a-time"></a>F: Kann ich mehrere Tests gleichzeitig durchführen?
 **A**: Ja. Verwenden Sie das Kontextmenü im **Projektmappen-Explorer**.

### <a name="q-should-i-add-a-data-source-before-or-after-i-generate-a-coded-test"></a>F: Sollte ich eine Datenquelle vor oder nach der Generierung eines codierten Tests hinzufügen?
 **A**: Es ist einfacher, eine [Datenquelle](../test/add-a-data-source-to-a-web-performance-test.md) hinzuzufügen, bevor Sie den codierten Test generieren, da der Code automatisch für Sie generiert wird.

 Wenn Sie einen codierten Test mit einer Datenquelle ausführen, wird möglicherweise folgende Fehlermeldung angezeigt:

 **Could not run test \<Test Name> on agent \<Computer Name>: Object reference not set to an instance of an object** (<Testname> konnte auf Agent <Computername> nicht ausgeführt werden: Objektverweis wurde nicht als Instanz eines Objekts festgelegt).

 Dieser Fehler kann auftreten, wenn Sie für die Testklasse ein DataSourceAttribute ohne ein zugehöriges DataBindingAttribute definiert haben. Um diesen Fehler zu beheben, fügen Sie ein entsprechendes DataBindingAttribute hinzu, löschen es oder kommentieren es aus dem Code aus.

### <a name="q-should-i-add-validation-and-extraction-rules-before-or-after-i-generate-a-coded-test"></a>F: Sollte ich Validierung und Extraktionsregeln vor oder nach der Generierung eines codierten Tests hinzufügen?
 **A**: Es einfacher, Validierungsregeln und Extraktionsregeln hinzuzufügen, bevor Sie den codierten Test generieren; zu Validierungszwecken sollten Sie jedoch [Tests der programmierten UI](../test/use-ui-automation-to-test-your-code.md) verwenden.