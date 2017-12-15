---
title: Senden eines Auftrags zum Trainieren eines Modells in Azure Batch AI
description: Training Model Cloud
keywords: KI, Visual Studio, Modell trainieren, Cloud
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: how-to article
ms.technology: visual studio
ms.devlang: multiple
ms.service: multiple
ms.openlocfilehash: d8289a482bc83741a6b6bf31499925f5d24d0192
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="train-ai-models-in-azure-batch-ai"></a>Trainieren von KI-Modellen in Azure Batch AI

Azure Batch AI ist ein verwalteter Dienst, mit dem Datenanalysten und KI-Forscher KI und andere Machine Learning-Modelle in Clustern von virtuellen Azure-Computern trainieren können (inkl. VMs mit GPU-Unterstützung). Sie müssen nur beschreiben, welche Anforderungen für den Auftrag bestehen und wo die Eingaben zu finden sind sowie die Ausgaben speichern, und Batch AI übernimmt den Rest. [Weitere Informationen zu Azure Batch AI](https://docs.microsoft.com/azure/batch-ai/overview) 

Da Batch AI mit den Visual Studio-Tools für KI integriert wird, können Sie Trainingsmodelle in Azure dynamisch horizontal hochskalieren.  Wenn Sie die [Visual Studio-Tools für KI](installation.md) installiert haben, lässt sich anhand der Anleitungen im Azure Machine Learning-Beispielkatalog ganz einfach ein neues Python-Projekt erstellen.

1. Starten Sie Visual Studio. Öffnen Sie den **Server-Explorer**, indem Sie das Menü **AI Tools** (KI-Tools) öffnen und auf **Cluster auswählen** klicken.  

    ![Clusterauswahl](media\train-model\select-cluster.png)

     
2. Erweitern Sie **AI Tools** (KI-Tools). Jede Ihrer Batch AI-Ressourcen wird automatisch erkannt und im Server-Explorer angezeigt. 
    
    ![Beispielkatalog](media\train-model\batchai.png)

3. Klicken Sie auf **Ansicht > Team Explorer…**, um das Fenster **Team Explorer** zu öffnen. Von dort können Sie eine Verbindung zu GitHub oder Visual Studio Team Services herstellen oder ein Repository klonen.

    ![Das Team Explorer-Fenster zeigt Visual Studio Team Services, GitHub und das Klonen eines Repositorys.](media\train-model\team-explorer.png)

4. Geben Sie in das URL-Feld unter **Lokale Git-Repositorys** `https://github.com/Microsoft/samples-for-ai` ein. Geben Sie dann einen Ordner für die geklonte Dateien ein, und klicken Sie auf **Klonen**.

    > [!Tip]
    > Der Ordner, den Sie in Team Explorer angeben, empfängt die geklonten Dateien. Im Gegensatz zum Befehl `git clone` wird beim Erstellen eines Klons in Team Explorer nicht automatisch ein Unterordner mit dem Namen des Repositorys erstellt.

5. Wenn das Klonen abgeschlossen ist, klicken Sie auf **Datei > Projektmappe öffnen > Projekt/Projektmappe**.
    
    ![Beispielkatalog](media\train-model\open-solution.png)

5. Öffnen Sie **samples-for-ai\TensorFlowExamples\TensorFlowExamples.sln** im Verzeichnis, das Sie im Repository geklont haben. 

    ![Beispielkatalog](media\train-model\tensorflowexamples.png)

5. Legen Sie das MNIST-Projekt als Startprojekt fest.

    ![Beispielkatalog](media\train-model\mnist-startup.png)

1. Klicken Sie mit der rechten Maustaste auf das MNIST-Projekt und dann auf **Auftrag übermitteln**.

    ![Beispielkatalog](media\train-model\submit-job.png)

1. Wählen Sie Ihr **Azure Batch AI**-Cluster aus, und klicken Sie auf **Importieren**. Wählen Sie die Datei `AzureBatchAI_TF_MNIST.json` aus, um schnell einige Standardwerte wie das zu verwendende Docker-Image aufzufüllen. Klicken Sie dann auf **Senden**.

    ![Beispielkatalog](media\train-model\submit-batch.png)