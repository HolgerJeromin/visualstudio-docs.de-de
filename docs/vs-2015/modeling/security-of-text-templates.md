---
title: Sicherheit von Textvorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, security
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 4ce9ccca0a144de7101e886712105315ec64fa75
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47510902"
---
# <a name="security-of-text-templates"></a>Sicherheit von Textvorlagen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Sicherheit von Textvorlagen](https://docs.microsoft.com/visualstudio/modeling/security-of-text-templates).  
  
Textvorlagen haben die folgenden Sicherheitsaspekte:  
  
-   Textvorlagen sind anfällig für Einfügen von beliebigem Code.  
  
-   Wenn der Mechanismus, den vom Host verwendet wird, finden Sie einen anweisungsprozessor nicht sicher ist, könnte ein böswilliger Direktivenprozessor ausgeführt werden.  
  
## <a name="arbitrary-code"></a>Beliebigen Code  
 Wenn Sie eine Vorlage schreiben, Sie können Code einfügen, alle innerhalb der \<## > Tags. Dies kann beliebigen Code innerhalb einer Textvorlage ausgeführt werden.  
  
 Achten Sie darauf, dass Sie Vorlagen aus vertrauenswürdigen Quellen abrufen. Stellen Sie sicher, dass die Warnung, die Endbenutzer Ihrer Anwendung nicht auf Vorlagen ausführen können, die nicht von vertrauenswürdigen Quellen stammen.  
  
## <a name="malicious-directive-processor"></a>Böswillige Direktivenprozessor  
 Das Textvorlagenmodul interagiert mit einem Transformationshost "und"-anweisungsprozessoren für eine oder mehrere ", um den Text der Vorlage in eine Ausgabedatei zu transformieren. Weitere Informationen finden Sie unter [das Textvorlagen-Transformationsprozess](../modeling/the-text-template-transformation-process.md).  
  
 Wenn der Mechanismus, den vom Host verwendet wird, finden Sie einen anweisungsprozessor nicht sicher ist, wird das Risiko der Ausführung eines böswilligen Direktivenprozessors ausgeführt. Der böswillige Direktivenprozessor kann Code, der ausgeführt wird, in bereitstellen `FullTrust` Modus aus, wenn die Vorlage ausgeführt wird. Wenn Sie eine benutzerdefinierte Textvorlagen-Transformationshost erstellen, müssen Sie einen sicheren Mechanismus, wie z. B. der Registrierung für die Engine für anweisungsprozessoren suchen verwenden.



