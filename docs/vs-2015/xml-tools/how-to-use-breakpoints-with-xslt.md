---
title: 'Vorgehensweise: Verwenden von Haltepunkten bei XSLT | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf7bbc2c-71dc-4cac-a6fc-add6b27d92ed
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 30ddb1fa8d56a55c5fc7a9811e4c836cabe4da0c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47513151"
---
# <a name="how-to-use-breakpoints-with-xslt"></a>Gewusst wie: Verwenden von Haltepunkten bei XSLT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sie können Haltepunkte in einem XSLT-Stylesheet oder im XML-Quelldokument festlegen. Wenn Sie einen Haltepunkt für ein Tag festlegen, wird der Haltepunkt beim Starten der Ausführung zur nächsten Anweisung verschoben, die über Quellzeileninformationen verfügt.  
  
 Weitere Informationen finden Sie unter [Grundlagen des Debuggens: Haltepunkte](http://msdn.microsoft.com/en-us/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e).  
  
## <a name="set-a-breakpoint-in-a-style-sheet"></a>Festlegen eines Haltepunkts in einem Stylesheet  
 Haltepunkte können für Starttags, Endtags und Textknoten eines XSLT-Stylesheets festgelegt werden. Haltepunkte können auch für Code in einem Skriptblock festgelegt werden.  
  
#### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>So legen Sie einen Haltepunkt in einem Stylesheet fest  
  
1.  Öffnen Sie ein Stylesheet im XML-Editor.  
  
2.  Positionieren Sie den Cursor an der Position des Haltepunkts, mit der rechten Maustaste, zeigen Sie auf **Haltepunkt**, und klicken Sie auf **Haltepunkt einfügen**.  
  
3.  Klicken Sie auf die Schaltfläche "Durchsuchen" (**...** ) auf die **Eingabe** Eigenschaftenfenster des Dokuments im Feld.  
  
4.  Suchen Sie das XML-Quelldokument, und klicken Sie auf **öffnen**.  
  
     Damit legen Sie die Quelldokumentdatei fest, die für die XSLT-Transformation verwendet wird.  
  
5.  Klicken Sie auf die **XSLT Debuggen** auf der Symbolleiste des XML-Editor.  
  
## <a name="set-a-breakpoint-in-an-xml-source-document"></a>Festlegen eines Haltepunkts in einem XML-Quelldokument  
 Haltepunkte können für Elemente, Attribute, Namespaceknoten, Kommentare, Verarbeitungsanweisungen und Textknoten eines XML-Quelldokuments festgelegt werden. Für den Dokumentknoten oder einen Namespaceknoten, der vom übergeordneten Element erbt, kann kein Haltepunkt festgelegt werden.  
  
#### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>So legen Sie einen Haltepunkt in einem XML-Quelldokument fest  
  
1.  Öffnen Sie das XML-Dokument im XML-Editor.  
  
2.  Positionieren Sie den Cursor an der Position des Haltepunkts, mit der rechten Maustaste, zeigen Sie auf **Haltepunkt**, und klicken Sie auf **Haltepunkt einfügen**.  
  
3.  Klicken Sie auf die Schaltfläche "Durchsuchen" (**...** ) auf die **Stylesheet** Eigenschaftenfenster des Dokuments im Feld.  
  
4.  Suchen Sie das XML-Quelldokument, und klicken Sie auf **öffnen**.  
  
     Damit legen Sie die Quelldokumentdatei fest, die für die XSLT-Transformation verwendet wird.  
  
5.  Klicken Sie auf die **XSLT Debuggen** auf der Symbolleiste des XML-Editor.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Debuggen eines XSLT-Stylesheets](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)

