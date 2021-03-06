---
title: Verwenden von Visual Studio zum Erstellen einer ASP.NET Core-Web-App in C#
description: Dieser Artikel enthält eine exemplarische Vorgehensweise zum Erstellen einer einfachen „Hallo Welt“-Web-App mit C# und ASP.NET Core.
ms.custom: mvc
ms.date: 09/23/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: quickstart
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 53bed90ea686897c2a668ddbc64c60a95c8edfe8
ms.sourcegitcommit: 25fc9605ba673afb51a24ce587cf4304b06aa577
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "47028935"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Schnellstart: Verwenden von Visual Studio zum Erstellen Ihrer ersten ASP.NET Core-Web-App

In dieser 5-10-minütigen Einführung in die Bedienung von Visual Studio erstellen Sie eine einfache Hallo-Welt-Web-App unter Verwendung einer ASP.NET-Projektvorlage und der Programmiersprache C#.

Wenn Sie Visual Studio noch nicht installiert haben, können Sie es auf der Seite [Visual Studio-Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) kostenlos herunterladen.

## <a name="create-a-project"></a>Erstellen eines Projekts

Zunächst müssen Sie ein Projekt für die ASP.NET Core-Webanwendung erstellen. Gehen Sie folgendermaßen vor:

1. Öffnen Sie Visual Studio 2017.

1. Klicken Sie in der Menüleiste im oberen Bereich auf **Datei** > **Neu** > **Projekt**.

1. Klappen Sie im linken Bereich des Dialogfelds **Neues Projekt** den Eintrag **Visual C#** auf, und wählen Sie **.NET Core** aus. Klicken Sie im mittleren Bereich auf **ASP.NET Core-Web-App**. Benennen Sie Ihre Datei anschließend mit `HelloWorld` und wählen Sie **OK**.

1. Überprüfen Sie im oberen Dropdownmenü des Dialogfelds **Neue ASP.NET Core-Webanwendung**, ob **ASP.NET Core 2.0** angezeigt wird. Wählen Sie dann **Webanwendung** und anschließend **OK** aus.

   ![Ansicht der animierten GIF-Datei, auf der gezeigt wird, wie ein C#-ASP.NET Core-Projekt in Visual Studio erstellt wird](../ide/media/csharp-aspnet-animated-create-project.gif)

   Im Anschluss wird Ihre Projektdatei in Visual Studio geöffnet.

   > [!NOTE]
   > Falls Sie die Projektvorlagenkategorie **.NET Core** nicht finden, klicken Sie im linken Bereich auf den Link **Visual Studio-Installer öffnen**.
   >
   > ![Den Visual Studio-Installer im Dialogfeld „Neues Projekt“ öffnen](../ide/media/open-visual-studio-installer.png)
   >
   > Der Visual Studio-Installer wird gestartet. Klicken Sie auf die Workload **ASP.NET und Webentwicklung** und anschließend auf **Ändern**.
   >
   > ![ASP.NET-Workload in VS-Installer](../ide/media/quickstart-aspnet-workload.png)
   >
   > (Möglicherweise müssen Sie Visual Studio schließen, bevor Sie die Installation des neuen Workloads fortsetzen können.)

## <a name="create-and-run-the-app"></a>Erstellen und Ausführen der App

Erstellen Sie anschließend eine Hallo-Welt-Web-App, und führen Sie diese aus. Gehen Sie folgendermaßen vor:

1. Erweitern Sie in Visual Studio im **Projektmappen-Explorer** den Ordner **Seiten**. Wählen Sie dann die Datei **About.cshtml** aus.

   ![Auswählen der About-cshtml-Datei im Projektmappen-Explorer](../ide/media/csharp-aspnet-about-page-html-file.png)

   Diese Datei entspricht der Seite mit der Bezeichnung **Info** in der Web-App, die im Webbrowser ausgeführt wird.

   ![Die Seite „Info“ in der Web-App](../ide/media/csharp-aspnet-about-page.png)

1. Ändern Sie im Visual Studio-Code-Editor den Text für weitere Informationen in „**Hallo Welt!**“.

1. Erweitern Sie im **Projektmappen-Explorer** den Ordner **About.cshtml**, und wählen Sie die **About.cshtml.cs**.

1. Ändern Sie den Text „Anwendungsbeschreibung“ in „**Wie lautet meine Nachricht?**“.

1. Klicken Sie auf **IIS Express**, oder drücken Sie **STRG**+**F5**, um die App auszuführen und im Webbrowser zu öffnen.

   ![Ansicht der animierten GIF-Datei, auf der gezeigt wird, wie eine C#-ASP.NET Core-Web-App in Visual Studio erstellt und ausgeführt wird](../ide/media/csharp-aspnet-animated-hello-world.gif)

   > [!NOTE]
   > Wenn Sie die Fehlermeldung **Es kann keine Verbindung mit dem Webserver „IIS Express“ hergestellt werden.** erhalten, schließen Sie Visual Studio. Öffnen Sie dann Visual Studio, indem Sie im Kontextmenü auf die Option **Als Administrator ausführen** klicken. Führen Sie die Anwendung anschließend erneut aus.

1. Überprüfen Sie im Webbrowser, ob auf der Seite **Info** Ihr aktualisierter Text angezeigt wird.

1. Schließen Sie den Webbrowser.

Damit haben Sie den Schnellstart erfolgreich abgeschlossen. Wir hoffen, dass Sie etwas über C#, ASP.NET Core und die Visual Studio-IDE (Integrierte Entwicklungsumgebung) gelernt haben.

## <a name="next-steps"></a>Nächste Schritte

Fahren Sie für weitere Informationen mit dem folgenden Tutorial fort:

> [!div class="nextstepaction"]
> [Erste Schritte mit C# und ASP.NET in Visual Studio](tutorial-csharp-aspnet-core.md)

## <a name="see-also"></a>Siehe auch

[Veröffentlichen Ihrer Web-App in Azure App Service mit Visual Studio](..//deployment/quickstart-deploy-to-azure.md)
