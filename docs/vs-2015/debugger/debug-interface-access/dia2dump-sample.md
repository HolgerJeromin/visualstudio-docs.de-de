---
title: Dia2dump-Beispiel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sample applications [DIA SDK]
- Dia2dump sample [DIA SDK]
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 410d4e8cf2a63c7d01058e501391f02543b1eee7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47520541"
---
# <a name="dia2dump-sample"></a>Dia2dump-Beispiel
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Dia2dump-Beispiel](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/dia2dump-sample).  
  
Dia2dump-Beispiel mit Visual Studio installiert ist und die Quelldatei dia2dump.cpp enthält. Die kompilierte ausführbare Datei ausgeführt wird, von der Befehlszeile aus und zeigt den Inhalt von einem gesamten Programmdatenbankdatei (.pdb).  
  
### <a name="to-install-the-sample"></a>So installieren Sie das Beispiel  
  
1.  Stellen Sie sicher, dass das System alle in der Visual Studio-Setup-Startseite beschriebene setupanforderungen erfüllt.  
  
2.  Installieren von Visual Studio aus, und befolgen Sie alle Setup und Installation-Anweisungen für diese enthaltenen Beispiele.  
  
#### <a name="to-build-the-sample"></a>So erstellen Sie das Beispiel  
  
1.  Öffnen Sie die Datei Dia2dump.sln in Visual Studio. (Falls erforderlich, Visual Studio zunächst das Dia2dump-Projekt aktualisieren, helfen Ihnen.)  
  
2.  In den Eigenschaftenseiten des Projekts in der **C/C++-** &#124; **allgemeine** &#124; **Additional Include Directories** -Eigenschaft, geben Sie die `..\DIA SDK\include` Verzeichnis. Dadurch wird sichergestellt, dass der Compiler die Datei dia2.h finden kann.  
  
3.  Auf der **erstellen** Menü klicken Sie auf **Projektmappe neu erstellen**.  
  
4.  Schließen Sie Visual Studio.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie eine Eingabeaufforderung, und geben Sie Folgendes:  
  
    ```  
    dia2dump filename  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Quelldatei Dia2dump.cpp](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)   
 [Gewusst wie: Problembehandlung bei nicht erfolgreichen Visual Studio-Projektupgrades](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)



