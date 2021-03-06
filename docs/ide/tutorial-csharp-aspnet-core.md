---
title: Erste Schritte mit C# und ASP.NET Core in Visual Studio
description: Dieser Artikel enthält eine ausführliche Anleitung zum Erstellen einer ASP.NET Core-Web-App mit C# in Visual Studio.
ms.custom: ''
ms.date: 09/17/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: d0e337ebb97b487adfd79be43ddc1301612ba090
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46496115"
---
# <a name="tutorial-get-started-with-c-and-aspnet-core-in-visual-studio"></a>Tutorial: Erste Schritte mit C# und ASP.NET Core in Visual Studio

In diesem Tutorial für die C#-Entwicklung mit ASP.NET Core in Visual Studio werden wir eine C#-ASP.NET Core-Web-App erstellen, Änderungen daran vornehmen, einige Funktionen der IDE kennenlernen und die App dann ausführen.

Wenn Sie Visual Studio noch nicht installiert haben, können Sie es auf der Seite [Visual Studio-Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) kostenlos herunterladen.

## <a name="create-a-project"></a>Erstellen eines Projekts

Zunächst erstellen Sie ein ASP.NET Core-Projekt. Schon bevor Sie mit der Bearbeitung beginnen, enthält der Projekttyp alle Vorlagendateien, die Sie für eine voll funktionsfähige Website benötigen.

1. Öffnen Sie Visual Studio 2017.

2. Klicken Sie in der Menüleiste im oberen Bereich auf **Datei** > **Neu** > **Projekt**. 

3. Erweitern Sie im Dialogfeld **Neues Projekt** links den Eintrag **Visual C#** und anschließend **Web**, und klicken Sie auf **.NET Core**. Klicken Sie im mittleren Bereich auf **ASP.NET Core-Web-App**. Nennen Sie die Datei *MyCoreApp*, und klicken Sie auf **OK**.

   ![Projektvorlage „ASP.NET Core-Webanwendung“ im Dialogfeld „Neues Projekt“ in der Visual Studio-IDE](../ide/media/csharp-aspnet-choose-template-name-razor-mycoreapp-file.png)

### <a name="add-a-workload-optional"></a>Hinzufügen einer Workload (optional)

Wenn Ihnen die Projektvorlage **ASP.NET Core-Webanwendung** fehlt, fügen Sie einfach die Workload **ASP.NET und Webentwicklung** hinzu. Sie haben folgende Möglichkeiten für das Hinzufügen der Workload, je nachdem, welche Visual Studio 2017-Updates auf dem Computer installiert sind.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Option 1: Über das Dialogfeld „Neues Projekt“

1. Klicken Sie im Dialogfeld **Neues Projekt** im linken Bereich auf den Link **Visual Studio-Installer öffnen**.

   ![Link „Visual Studio-Installer öffnen“ im Dialogfeld „Neues Projekt“](../ide/media/open-visual-studio-installer-mycoreapp.png)

1. Der Visual Studio-Installer wird gestartet. Klicken Sie auf die Workload **ASP.NET und Webentwicklung** und anschließend auf **Ändern**.

   ![Workload für die plattformübergreifende .NET Core-Entwicklung im Visual Studio-Installer](../ide/media/quickstart-aspnet-workload.png)

   (Möglicherweise müssen Sie Visual Studio schließen, bevor Sie die Installation des neuen Workloads fortsetzen können.)

#### <a name="option-2-use-the-tools-menu-bar"></a>Option 2: Über die Menüleiste „Extras“

1. Schließen Sie das Dialogfeld **Neues Projekt**. Wählen Sie dann in der oberen Menüleiste **Extras** > **Get Tools and Features** (Tools und Features abrufen) aus.

1. Der Visual Studio-Installer wird gestartet. Klicken Sie auf die Workload **ASP.NET und Webentwicklung** und anschließend auf **Ändern**.

   (Möglicherweise müssen Sie Visual Studio schließen, bevor Sie die Installation des neuen Workloads fortsetzen können.)

### <a name="add-a-project-template"></a>Hinzufügen einer Projektvorlage

1. Klicken Sie im Dialogfeld **Neue ASP.NET Core-Webanwendung** auf die Projektvorlage **Webanwendung**.

1. Überprüfen Sie, ob **ASP.NET Core 2.1** im oberen Dropdownmenü angezeigt wird. Klicken Sie dann auf **OK**.

   ![Dialogfeld „Neue ASP.NET Core-Webanwendung“](../ide/media/new-project-csharp-aspnet-razor-web-app.png)

### <a name="about-your-solution"></a>Die Projektmappe

Diese Lösung verwendet das **Razor Pages**-Entwurfsmuster. Das unterscheidet sich vom Entwurfsmuster [Model View Controller (MVC)](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x) dadurch, dass es so optimiert ist, dass es den Modell- und Controllercode selbst in die Razor Pages-Seite einfügt.

## <a name="tour-your-solution"></a>Kennenlernen der Projektmappe

 1. Die Projektvorlage erstellt eine Projektmappe mit einem einzelnen ASP.NET Core-Projekt namens _MyCoreApp_. Wählen Sie die Registerkarte **Projektmappen-Explorer** aus, um den Inhalt anzuzeigen.

    ![ASP.NET-Projektmappen-Explorer in Visual Studio für die Razor Pages-Lösung namens MyCoreApp](../ide/media/csharp-aspnet-razor-solution-explorer-mycoreapp.png)

 1. Erweitern Sie den Ordner **Seiten** und dann *About.cshtml*.

     ![Datei „About.cshtml“ im Projektmappen-Explorer in Visual Studio](../ide/media/csharp-aspnet-razor-solution-explorer-aboutcshtml.png)

 1. Zeigen Sie die Datei **About.cshtml** im Code-Editor an.

     ![Anzeigen der Datei „About.cshtml“ im Visual Studio-Code-Editor](../ide/media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code.png)

 1. Wählen Sie die Datei **About.cshtml.cs** aus.

     ![Auswählen der Datei „About.cshtml.cs“ im Visual Studio-Code-Editor](../ide/media/csharp-aspnet-razor-solution-explorer-aboutcshtmlcs.png)

 1. Zeigen Sie die Datei **About.cshtml.cs** im Code-Editor an.

     ![Anzeigen der Datei „About.cshtml“ im Visual Studio-Code-Editor](../ide/media/csharp-aspnet-razor-aboutcshtmlcs-mycoreapp-code.png)

 1. Das Projekt enthält den Ordner **wwwroot**, der das Stammverzeichnis Ihrer Website ist. Erweitern Sie den Ordner, um den Inhalt anzuzeigen.

     ![Ordner „wwwroot“ im Projektmappen-Explorer in Visual Studio](../ide/media/csharp-aspnet-razor-solution-explorer-wwwroot.png)

    Sie können statische Websiteinhalte wie CSS, Bilder und JavaScript-Bibliotheken direkt in die gewünschten Pfade einfügen.

 1. Das Projekt enthält auch Konfigurationsdateien, die die Web-App zur Laufzeit verwalten. Die [Standardkonfiguration](/aspnet/core/fundamentals/configuration) der Anwendung befindet sich in der Datei *appsettings.json*. Sie können diese Einstellungen jedoch auch mit *appsettings.Development.json* überschreiben. Erweitern Sie die Datei **appsettings.json**, um die Datei **appsettings.Development.json** anzuzeigen.

     ![Konfigurationsdateien im Projektmappen-Explorer in Visual Studio](../ide/media/csharp-aspnet-razor-solution-explorer-appsettingsjson.png)

## <a name="run-debug-and-make-changes"></a>Ausführen, Debuggen und Vornehmen von Änderungen

1. Klicken Sie in der IDE auf die Schaltfläche **IIS Express**, um die App im Debugmodus zu erstellen und auszuführen. (Alternativ können Sie **F5** drücken oder in der Menüleiste **Debuggen** > **Debuggen starten** auswählen.)

     ![Die Schaltfläche „IIS Express“ in Visual Studio](../ide/media/csharp-aspnet-razor-iisexpress.png)

     > [!NOTE]
     > Wenn Sie die Fehlermeldung **Es kann keine Verbindung mit dem Webserver "IIS Express" hergestellt werden.** erhalten, schließen Sie Visual Studio. Öffnen Sie dann Visual Studio, indem Sie im Kontextmenü auf die Option **Als Administrator ausführen** klicken. Führen Sie die Anwendung anschließend erneut aus.

1. Visual Studio startet ein Browserfenster. In der Menüleiste sollten die Seiten **Startseite**, **Info** und **Kontakt** angezeigt werden. Wenn das nicht der Fall ist, wählen Sie das Menüelement „Hamburger“ aus, um sie anzuzeigen.

    ![Auswählen des Menüelements „Hamburger“ in der Menüleiste der Web-App](../ide/media/csharp-aspnet-razor-browser-page.png)

1. Wählen Sie in der Menüleiste **Info** aus.

   ![Auswählen von „Info“ in der Menüleiste im Browserfenster der App](../ide/media/csharp-aspnet-razor-browser-page-about-menu.png)

   Auf der Seite **Info** im Browser wird u.a. der Text gerendert, der in der Datei *About.cshtml* festgelegt ist.

   ![Text auf der Seite „About“](../ide/media/csharp-aspnet-razor-browser-page-about.png)

1. Lassen Sie das Browserfenster geöffnet, und kehren Sie zu Visual Studio zurück.

1. Wählen Sie in Visual Studio **About.cshtml** aus. Löschen Sie das Wort _changed_, und fügen Sie an derselben Stelle _file and directory_ ein.

    ![Ändern des Texts in der Datei „About.cshtml“](../ide/media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code-changed.png)

1. Wählen Sie **About.cshtml.cs** aus. Bereinigen Sie dann die `using`-Anweisungen oben in der Datei mithilfe der folgenden Verknüpfung.

   Wählen Sie eine der ausgegrauten `using`-Anweisungen aus, damit die Glühbirne für [Schnelle Aktionen](../ide/quick-actions.md) unter dem Caretzeichen oder am linken Rand angezeigt wird. Klicken Sie zunächst auf die Glühbirne und anschließend auf **Nicht benötigte Using-Direktiven entfernen**.

   ![Entfernen unnötiger Using-Anweisungen in der Datei „About.cshtml.cs“](../ide/media/csharp-aspnet-razor-remove-unnecessary-usings.png)

     Visual Studio löscht die unnötigen `using`-Anweisungen aus der Datei.

1. Ändern Sie dann in der `OnGet()`-Methode den Text in den folgenden Code:

     ```csharp
     public void OnGet()
     {
         string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
     }
    ```
1. **Environment** und **String** werden wellenförmig unterstrichen. Die Markierungen zeigen an, dass sich diese Typen nicht im gültigen Bereich befinden.

   ![Mit wellenförmigen Unterstrichen markierte Fehler in der OnGet-Methode](../ide/media/csharp-aspnet-razor-add-new-on-get-method.png)

    Öffnen Sie die Symbolleiste **Fehlerliste**. Dort werden dieselben Fehler aufgelistet. (Wenn Ihnen die Symbolleiste **Fehlerliste** nicht angezeigt wird, klicken Sie in der oberen Menüleiste auf **Ansicht** > **Fehlerliste**.)

   ![Fehlerliste in Visual Studio](../ide/media/csharp-aspnet-razor-error-list.png)

1. Korrigieren wir dies. Platzieren Sie den Cursor im Code-Editor auf einer Zeile, die den Fehler enthält, und wählen Sie anschließend am linken Rand die Glühbirne für schnelle Aktionen aus. Wählen Sie im Dropdownmenü **using System;** aus, um diese Anweisung am Anfang der Datei hinzuzufügen und die Fehler zu beheben.

   ![Hinzufügen der „using System;“-Anweisung](../ide/media/csharp-aspnet-razor-add-usings.png)

1. Drücken Sie **STRG**+**S**, um die Änderungen zu speichern und die App im Webbrowser zu aktualisieren.

1. Klicken Sie oben auf der Website auf **Info**, um die Änderungen anzuzeigen.

   ![Anzeigen der aktualisierten „Info“-Seite mit den gemachten Änderungen](../ide/media/csharp-aspnet-razor-browser-page-about-changed.png)

1. Schließen Sie den Webbrowser, drücken Sie **UMSCHALT**+**F5**, um den Debugmodus zu beenden, und schließen Sie dann Visual Studio.

## <a name="quick-answers-faq"></a>Schnelle Antworten zu häufig gestellten Fragen

Im folgenden kurzen Abschnitt zu häufig gestellten Fragen werden einige wichtige Konzepte besprochen.

### <a name="what-is-c"></a>Was ist C#?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) ist eine typsichere und objektorientierte Programmiersprache, die nicht nur stabil, sondern auch einfach zu erlernen ist.

### <a name="what-is-aspnet-core"></a>Was ist ASP.NET Core?

ASP.NET Core ist ein plattformübergreifendes Open Source-Framework zum Erstellen von Anwendungen mit Internetverbindung, wie etwa Web-Apps und -dienste. ASP.NET Core-Apps können unter .NET Core oder .NET Framework ausgeführt werden. Sie können Ihre ASP.NET Core-Apps plattformübergreifend unter Windows, macOS und Linux ausführen und entwickeln. ASP.NET Core ist auf [GitHub](https://github.com/aspnet/home) verfügbar.

### <a name="what-is-visual-studio"></a>Was ist Visual Studio?

Visual Studio ist eine integrierte Zusammenstellung von Entwicklertools, die die Produktivität fördern. Es ist also ein Programm zum Erstellen von Programmen und Anwendungen.

## <a name="next-steps"></a>Nächste Schritte

Damit haben Sie das Tutorial erfolgreich abgeschlossen. Wir hoffen, dass Sie etwas über C#, ASP.NET Core und die Visual Studio-IDE gelernt haben. Weitere Informationen zum Erstellen einer Web-App oder Website mit C# und ASP.NET Core finden Sie in den folgenden Tutorials:

> [!div class="nextstepaction"]
> [Erstellen einer Razor-Seiten-Web-App mit ASP.NET Core](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

## <a name="see-also"></a>Siehe auch

[Veröffentlichen Ihrer Web-App in Azure App Service mit Visual Studio](..//deployment/quickstart-deploy-to-azure.md)