---
title: Status der Aktivitäts-Designer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.State.UI
ms.assetid: 9455ab37-93a0-4c46-9eb8-b6611ca23167
caps.latest.revision: 5
author: steved0x
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 3c1d0019179d0a8e3f82001c371e760172251c2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524153"
---
# <a name="state-activity-designer"></a>Zustandsaktivitäts-Designer
<xref:System.Activities.Statements.State> stellt einen Zustand dar, in dem sich ein Zustandsautomat befinden kann.  
  
## <a name="using-the-state-activity-designer"></a>Verwenden des Zustandsaktivitäts-Designers  
 Hinzufügen einer <xref:System.Activities.Statements.State> in einem Workflow ziehen die **Zustand** Aktivitäts-Designer aus der **State Machine** im Abschnitt der **Toolbox** und legen ihn auf eine <xref:System.Activities.Statements.StateMachine> auf der [!INCLUDE[wfd1](../includes/wfd1-md.md)] Oberfläche. Eine <xref:System.Activities.Statements.State>-Aktivität kann auf einem <xref:System.Activities.Statements.StateMachine> abgelegt werden, und es können später Übergänge hinzugefügt werden, oder es kann ein Übergang erstellt werden, wenn die <xref:System.Activities.Statements.State>-Aktivität abgelegt wird. Hinzufügen einer <xref:System.Activities.Statements.State> Aktivität, und erstellen Sie einen Übergang in einem Schritt, ziehen Sie eine **Zustand** Aktivität aus der **State Machine** im Abschnitt der **Toolbox** und zeigen sie eine andere der Zustand im Workflow-Designer. Sobald sich der gezogene <xref:System.Activities.Statements.State> über einem anderen <xref:System.Activities.Statements.State> befindet, werden vier Dreiecke um den anderen <xref:System.Activities.Statements.State> herum eingeblendet. Wenn <xref:System.Activities.Statements.State> auf einem der vier Dreiecke abgelegt wird, wird er dem Zustandsautomaten hinzugefügt, und es wird ein Übergang vom Quell-<xref:System.Activities.Statements.State> zum abgelegten Ziel-<xref:System.Activities.Statements.State> erstellt. Weitere Informationen finden Sie unter [Übergang](../workflow-designer/transition-activity-designer.md).  
  
### <a name="state-activity-properties-in-the-workflow-designer"></a>Zustandsaktivitätseigenschaften im Workflow-Designer  
 In der folgenden Tabelle sind die <xref:System.Activities.Statements.State>-Eigenschaften aufgeführt, die mithilfe des Workflow-Designers festgelegt werden können, und es wird beschrieben, wie sie im Designer verwendet werden. Einige dieser Eigenschaften können im Eigenschaftenraster und einige auf der Designeroberfläche bearbeitet werden.  
  
|Eigenschaftenname|Erforderlich|Verwendung|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|Gibt den benutzerfreundlichen Namen der <xref:System.Activities.Statements.State>Aktivität im Header an. Der Standardwert ist **Zustand**. Der Wert kann im Eigenschaftenraster oder direkt im Header des Aktivitätsdesigners bearbeitet werden. <xref:System.Activities.Statements.State.DisplayName%2A> wird in der Breadcrumbnavigation verwendet, die am oberen Rand des Workflow-Designers angezeigt wird.<br /><br /> Obwohl der <xref:System.Activities.Statements.State.DisplayName%2A> nicht zwingend erforderlich ist, wird empfohlen, einen Anzeigenamen zu verwenden.|  
|<xref:System.Activities.Statements.State.Entry%2A>|False|Gibt die Aktion an, die eintritt, wenn ein Übergang in diesen Zustand stattfindet. Wenn die <xref:System.Activities.Statements.State> -Aktivität erweitert wird, dieser Wert kann durch Ziehen einer Aktivität festgelegt werden die **Toolbox** per Drag & Drop auf die **Eintrag** -Abschnitt des Zustands.|  
|<xref:System.Activities.Statements.State.Exit%2A>|False|Gibt die Aktion an, die eintritt, wenn ein Übergang aus diesem Zustand stattfindet. Wenn die <xref:System.Activities.Statements.State> -Aktivität erweitert wird, dieser Wert kann durch Ziehen einer Aktivität festgelegt werden die **Toolbox** per Drag & Drop auf die **beenden** -Abschnitt des Zustands.|  
|<xref:System.Activities.Statements.State.Transitions%2A>|False|Listet die möglichen Übergänge auf, die von <xref:System.Activities.Statements.State> ausgehen. Jedes Element in der Liste weist einen Link zum verknüpften <xref:System.Activities.Statements.Transition> und zum Ziel-<xref:System.Activities.Statements.State> auf. Indem Sie auf den Link klicken, wechselt der Designer zur erweiterten Ansicht von <xref:System.Activities.Statements.Transition> oder <xref:System.Activities.Statements.State>.|  
  
## <a name="see-also"></a>Siehe auch  
 [StateMachine](../workflow-designer/statemachine-activity-designer.md)   
 [FinalState](../workflow-designer/finalstate-activity-designer.md)   
 [Transition](../workflow-designer/transition-activity-designer.md)