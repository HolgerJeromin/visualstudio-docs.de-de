---
title: 'Gewusst wie: Hinzufügen von Kommentaren zu einem Workflow im Workflow-Designer | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.Annotations.Annotation.UI
- Annotation
ms.assetid: 9aa0e8d6-8129-4438-8389-d460611581a7
caps.latest.revision: 7
author: steved0x
ms.author: gewarren
manager: erikre
ms.openlocfilehash: f70f8ba1a30d5adcaffe7e693fcc711d08a28baf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47513033"
---
# <a name="how-to-add-comments-to-a-workflow-in-the-workflow-designer"></a>Vorgehensweise: Hinzufügen von Kommentaren zu einem Workflow im Workflow-Designer
Um die Erstellung größerer, komplexerer Workflows zu erleichtern, bietet [!INCLUDE[net_v45](../includes/net-v45-md.md)] Entwicklern die Möglichkeit, den folgenden Elementtypen im Designer Anmerkungen hinzuzufügen:  
  
-   <xref:System.Activities.Activity>  
  
-   <xref:System.Activities.Statements.State>  
  
-   <xref:System.Activities.Statements.Transition>  
  
-   Von <xref:System.Activities.Statements.FlowNode> abgeleitete Klassen  
  
-   <xref:System.Activities.Variable>  
  
-   <xref:System.Activities.Argument>  
  
> [!IMPORTANT]
>  Der Inhalt einer Anmerkung wird im Nur-Text-Format in der XAML-Datei gespeichert, die dem Workflow zugeordnet ist, und kann möglicherweise von anderen gelesen werden. Bedenken Sie diesen Umstand, wenn Sie vertrauliche Informationen in eine Anmerkung einfügen.  
  
### <a name="adding-an-annotation-to-an-activity-in-the-designer"></a>Hinzufügen einer Anmerkung zu einer Aktivität im Designer  
  
1.  Der Workflow-Designer mit der Maustaste auf ein Element im Workflow Designer, und wählen **Anmerkungen**, **Anmerkung hinzufügen**.  
  
2.  Fügen Sie den Text der Anmerkung im angegebenen Bereich ein.  
  
3.  Für das Element wird ein Anmerkungssymbol angezeigt. Wenn Sie mit dem Mauszeiger auf das Anmerkungssymbol zeigen, wird der Text der Anmerkung angezeigt.  
  
     ![Sequence-Aktivität, die mit Anmerkung](../workflow-designer/media/annotation.png "Anmerkung")  
  
### <a name="displaying-an-annotation-in-an-activitys-designer"></a>Anzeigen einer Anmerkung im Designer einer Aktivität  
  
1.  Ein Aktivitäts-Designer mit einer Anmerkung, die außerhalb der Aktivität angezeigt, und klicken Sie auf die **Pin** Symbol im anmerkungsadorner.  
  
2.  Die Anmerkung wird im Aktivitäts-Designer angezeigt. Im unten stehenden Screenshot wird eine Anmerkung für die Startaktivität im Workflow im Aktivitäts-Designer angezeigt.  
  
     ![In der Aktivitäts-Designer angezeigte Anmerkung](../workflow-designer/media/annotationindesigner.png "AnnotationInDesigner")  
  
3.  Wenn die Anmerkung außerhalb der Aktivitäts Designer anzeigen möchten, zeigen Sie auf den anmerkungsbereich im Aktivitäts Designer, und klicken Sie auf die **Unpin** Symbol  
  
     ![Außerhalb eines Aktivitäts Designers angezeigte Anmerkung](../workflow-designer/media/annotationoutsidedesigner.png "AnnotationOutsideDesigner")  
  
### <a name="showing-or-hiding-all-annotations"></a>Ein- oder Ausblenden aller Anmerkungen  
  
1.  Klicken Sie mit der rechten Maustaste auf eine Aktivität, die eine Anmerkung enthält. Wählen Sie **Anmerkungen**, **alle Anmerkungen anzeigen**.  
  
2.  In den Aktivitäts-Designern werden alle Anmerkungen angezeigt.  
  
3.  Um alle Anmerkungen außerhalb der Aktivitäts Designer anzuzeigen, mit der Maustaste, auf die Aktivität, und wählen **Anmerkungen**, **alle Anmerkungen ausblenden**.  
  
### <a name="editing-or-deleting-an-annotation-for-an-activity"></a>Bearbeiten oder Löschen einer Anmerkung für eine Aktivität  
  
1.  Klicken Sie mit der rechten Maustaste auf eine Aktivität, die eine Anmerkung enthält.  
  
2.  Wählen Sie **Anmerkungen**, **Anmerkung bearbeiten** oder **Anmerkung löschen**.  
  
3.  Die Anmerkung wird zur Bearbeitung geöffnet oder gelöscht.  
  
4.  Um alle Anmerkungen gleichzeitig zu löschen, Maustaste den Workflow aus, und wählen **Anmerkung**, **alle Anmerkungen löschen**.  
  
### <a name="adding-editing-and-deleting-an-annotation-for-a-variable-or-argument"></a>Hinzufügen, Bearbeiten und Löschen einer Anmerkung für eine Variable oder ein Argument  
  
1.  Klicken Sie mit der rechten Maustaste auf eine Variable oder ein Argument, und wählen Sie Anmerkung hinzufügen.  
  
2.  Geben Sie den Text der Anmerkung ein. Für die Variable oder das Argument wird ein Anmerkungssymbol angezeigt.  
  
3.  Klicken Sie mit der rechten Maustaste auf eine Variable oder ein Argument, die bzw. das eine Anmerkung enthält. Wählen Sie Anmerkung bearbeiten aus.  
  
4.  Die Anmerkung wird zur Bearbeitung geöffnet.  
  
5.  Klicken Sie mit der rechten Maustaste auf eine Variable oder ein Argument, die bzw. das eine Anmerkung enthält. Wählen Sie Anmerkung löschen aus.  
  
6.  Die Anmerkung wird gelöscht.