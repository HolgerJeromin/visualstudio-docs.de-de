---
title: Konfigurieren von Zielen und Aufgaben | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6075eea96d217b029f7febb8bcf80aef2a47eb2
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151144"
---
# <a name="configure-targets-and-tasks"></a>Konfigurieren von Zielen und Aufgaben
Sie können MSBuild-Ziele und -Aufgaben so konfigurieren, dass sie prozessextern mit MSBuild ausgeführt werden, damit Sie auf Kontexte abzielen können, die sich von dem unterscheiden, in dem Sie die Ausführung eigentlich vorgesehen haben. Beispielsweise können Sie auf eine 32-Bit-.NET Framework 2.0-Anwendung abzielen, während der Entwicklungscomputer auf einem 64-Bit-.NET Framework 4.5-Betriebssystem ausgeführt wird. Sie können auch auf Computer abzielen die mit .NET Framework 4 oder früher ausgeführt werden. Die Kombination der 32- oder 64-Bitanzahl und der spezifischen .NET Framework-Version wird als der *Zielkontext* bezeichnet.  
  
## <a name="installation"></a>Installation  
 .NET Framework 4.5 und 4.5.1 ersetzen die Common Language Runtime (CLR) und die Ziele, Aufgaben und Tools von .NET Framework 4 , ohne sie umzubenennen. .NET Framework 4.5.1 wird als Teil von [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)] installiert.  
  
 Wenn Sie MSBuild von Visual Studio getrennt installieren möchten, können Sie das Installationspaket von der [MSBuild-Downloadsite](http://go.microsoft.com/fwlink/?LinkId=309745) herunterladen. Sie müssen außerdem die .NET Framework-Versionen installieren, die Sie verwenden möchten.  
  
## <a name="targets-and-tasks"></a>Ziele und Aufgaben  
 MSBuild führt bestimmte Buildaufgaben prozessextern aus, um auf mehr Kontexte abzuzielen.  Beispielsweise kann ein 32-Bit-MSBuild eine Buildaufgabe in einem 64-Bit-Prozess ausführen, um auf einen 64-Bit-Computer abzuzielen. Dies wird durch `UsingTask`-Argumente und `Task`-Parameter gesteuert. Die Ziele, die von .NET Framework 4.5 installiert werden, legen diese Argumente und Parameter fest, und es sind keine Änderungen erforderlich, um Anwendungen für die verschiedenen Zielkontexte zu erstellen.  
  
 Wenn Sie eigene Zielkontext erstellen möchten, müssen Sie diese Argumente und Parameter entsprechend festlegen. In der .NET Framework 4.5-Datei *Microsoft.Common.targets* und in der Datei *Microsoft.Common.Tasks* finden Sie einige Beispiele.  Informationen zum Erstellen einer benutzerdefinierten Aufgabe, die mehrere Zielkontexte verwenden kann, oder zum Ändern vorhandener Aufgaben finden Sie unter [Vorgehensweise: Konfigurieren von Zielen und Aufgaben](../msbuild/how-to-configure-targets-and-tasks.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Zielversionen](../msbuild/msbuild-multitargeting-overview.md)