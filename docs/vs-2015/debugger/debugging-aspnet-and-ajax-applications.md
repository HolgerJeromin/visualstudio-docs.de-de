---
title: Debuggen von ASP.NET- und AJAX-Anwendungen | Microsoft-Dokumentation
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
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- debugging ASP.NET Web applications
- debugging [ASP.NET], about ASP.NET debugging
- WCF, debugging
ms.assetid: 9d531913-541b-47b8-864d-138021fca0c6
caps.latest.revision: 34
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f81ca66b7f7d4dde596b465211cb92cec5e695ca
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47522740"
---
# <a name="debugging-aspnet-and-ajax-applications"></a>Debuggen von ASP.NET- und AJAX-Anwendungen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Debuggen von ASP.NET- und AJAX-Anwendungen](https://docs.microsoft.com/visualstudio/debugger/debugging-aspnet-and-ajax-applications).  
  
Das Debuggen von [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]-Webanwendungen ähnelt dem Debuggen von Windows Forms oder anderen Windows-Anwendungen, da beide Arten von Anwendungen Steuerelemente und Ereignisse enthalten. Aber es gibt auch grundlegende Unterschiede zwischen den beiden Anwendungsarten:  
  
-   Die Zustandsüberwachung ist in einer Webanwendung komplexer.  
  
-   In einer Windows-Anwendung befindet sich der zu debuggende Code meistens an einem Ort. Bei einer Webanwendung kann der Code auf dem Client und auf dem Server vorhanden sein. Obwohl sich der gesamte [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]-Code auf dem Server befindet, kann auf dem Client auch JavaScript- oder [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]-Code vorhanden sein.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorbereitungen zum Debuggen von ASP.NET](../debugger/preparing-to-debug-aspnet.md)  
 Beschreibt die erforderlichen Schritte, um das Debuggen von [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]-Anwendungen zu ermöglichen.  
  
 [Debuggen von Webanwendungen](../debugger/debugging-web-applications.md)  
 Erläutert das Debuggen einer [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]-Anwendung, einschließlich AJAX-fähiger Skriptanwendungen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verwalten von Ausnahmen mit dem Debugger](../debugger/managing-exceptions-with-the-debugger.md)  
 Erläutert, warum Nur mein Code zum Debuggen von [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]-Ausnahmen aktiviert werden muss.  
  
 [Debugging and Tracing Ajax Applications Overview](http://msdn.microsoft.com/library/92684ea0-7bb4-4a34-9203-3aa6394ce375)  
 Es werden einige Techniken und Tools erläutert, die Ihnen beim Debuggen Ihres AJAX-Codes helfen können.  
  
 [IntelliTrace](../debugger/intellitrace.md)  
 Debuggen Sie den Code schneller, indem Sie mit IntelliTrace einen Verlauf vom Zustand der Anwendung aufzuzeichnen und überprüfen, ohne die Anwendung so oft neu zu starten. Sie können Informationen zu Ereignissen und Aufrufen, die während der Ausführung der Anwendung auftreten, anzeigen und das Debuggen ab diesen Zeitpunkten starten. Erfordert Visual Studio Ultimate.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggersicherheit](../debugger/debugger-security.md)   
 [Debuggen von Webanwendungen und Skripts](../debugger/debugging-web-applications-and-script.md)   
 [Debuggereinstellungen und -vorbereitung](../debugger/debugger-settings-and-preparation.md)   
 [Debugger – Grundlagen](../debugger/debugger-basics.md)



