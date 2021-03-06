---
title: Azure-SDK für Python
description: Mit dem Azure SDK für Python können Microsoft Azure-Dienste von Python-Anwendungen genutzt werden, die auf beliebigen Plattformen ausgeführt werden.
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
- azure
ms.openlocfilehash: 6c7f38dbe58c5172c8480c88ae84c6e28f5d512b
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45545553"
---
# <a name="azure-sdk-for-python"></a>Azure-SDK für Python

Das Azure SDK für Python vereinfacht die Nutzung und Verwaltung von Microsoft Azure-Diensten in Anwendungen unter Windows, Mac OS X und Linux.

## <a name="installation"></a>Installation

Das Azure SDK wird über den [Python-Paketindex](https://pypi.python.org/pypi/azure) installiert.

Installieren Sie die **neueste stabile Version** (unterstützt Python 2.7 und 3.x) wie folgt:

```command
pip install azure
```

Sie können auch den entsprechenden Artikel der Azure-Dokumentation lesen: [Installieren von Python und SDK](https://docs.microsoft.com/azure/python-how-to-install/).

## <a name="documentation"></a>Dokumentation

Unter [azure-sdk-for-python.readthedocs.org](https://docs.microsoft.com/en-us/python/azure/?view=azure-python) finden Sie die entsprechende Dokumentation.

Das [Python Developer Center](https://azure.microsoft.com/develop/python/) umfasst ebenfalls eine Reihe nützlicher Ressourcen für das Azure SDK für Python, darunter eine Reihe von Tutorials:

- Erstellen von Web-Apps mit [Django](/azure/app-service-web/web-sites-python-create-deploy-django-app) [Flask](/azure/app-service-web/web-sites-python-create-deploy-flask-app) und [Bottle](/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
- [Blobspeicher](/azure/storage/storage-python-how-to-use-blob-storage)
- [Tabellenspeicher](/azure/storage/storage-python-how-to-use-table-storage)
- [Warteschlangenspeicher](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- [Service Bus-Warteschlangen](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [Service Bus-Themen und -Abonnements](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Dienstverwaltung](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Bei öffentlichen APIs ohne Dokumentation sind die Komponententests im [GitHub-Repository für das SDK](https://github.com/Azure/azure-sdk-for-python) eine gute Informationsquelle:

- [Komponententests für Speicher](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Komponententests für Service Bus](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Komponententests für die Dienstverwaltung](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)

## <a name="support"></a>Unterstützung

Das Git-Repository für das SDK befindet sich unter [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python).

Wenn Ihnen Fehler auffallen oder Sie Fragen zur Verwendung des SDK haben, [melden Sie Probleme im Repository](https://github.com/Azure/azure-sdk-for-python/issues).
