---
title: Verwenden des Aktivitätsdesigners der Vorgängerversion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- activities, configuring
- custom activities
- Activity Designer
- child activities, adding
- activities, adding child
- activities, creating custom
ms.assetid: 2fea8a05-6e58-423d-94bf-a822b15ffb80
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: a3970a4453c23a47b609886c24d0b8fe62efd3e4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47522694"
---
# <a name="using-the-legacy-activity-designer"></a>Verwenden des Aktivitätsdesigners der Vorgängerversion
In diesem Thema wird beschrieben, wie der Aktivitätsdesigner in der Vorgängerversion von [!INCLUDE[wfd1](../includes/wfd1-md.md)] verwendet wird. Verwenden Sie den Designer der Vorgängerversion, wenn Sie auf [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] oder [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] abzielen möchten.  
  
 Mit dem Aktivitätsdesigner können Sie benutzerdefinierte Aktivitäten erstellen.  
  
## <a name="creating-a-custom-activity"></a>Erstellen einer benutzerdefinierten Aktivität  
 Führen Sie die nachstehenden Schritte aus, um mit dem Aktivitätsdesigner eine benutzerdefinierte Aktivität zu erstellen:  
  
1.  Auf der **Projekt** Menü klicken Sie auf **Aktivität hinzufügen**.  
  
2.  Wählen Sie die **Aktivität** oder **Aktivität (mit getrenntem Code)** Vorlage.  
  
    1.  Verwenden der **Aktivität** Vorlage zum Erstellen einer Aktivität mit der Aktivitätsdefinition und dem Benutzercode in derselben Codedatei.  
  
    2.  Verwenden der **Aktivität (mit getrenntem Code)** Vorlage zum Erstellen einer Aktivität mit der als Workflowmarkup und dem Benutzercode in einer eigenen Codedatei ausgedrückte Aktivitätsdefinition.  
  
3.  Geben Sie einen Aktivitätsnamen oder behalten Sie den Standardnamen, und klicken Sie dann auf **hinzufügen**.  
  
 Sie können auch einen Satz von benutzerdefinierten Aktivitäten erstellen, durch das Erstellen eines neuen Projekts vom Typ **Workflowaktivitätsbibliothek**. Weitere Informationen zu diesem Projekttyp finden Sie unter [Vorgehensweise: Erstellen einer Workflowaktivitätsbibliothek (Vorgängerversion)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md).  
  
## <a name="configuring-an-activity"></a>Konfigurieren einer Aktivität  
 Wenn der Aktivitätsdesigner aktiv ist, können Sie mit dem Eigenschaftenbrowser die in der folgenden Tabelle aufgeführten Eigenschaften konfigurieren.  
  
|Eigenschaft|Kommentare|  
|--------------|--------------|  
|**Name**|Der Name der Aktivität.|  
|**Basisklasse**|Die Basisklasse, von der die Aktivität abgeleitet wird. Die Standardbasisklasse ist [SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020). In der **Eigenschaften** Fenster, klicken Sie auf die **Basisklasse** Ellipsen **[...]**  eine andere Basisklasse im Auswählen der [navigieren, und wählen Sie eine .NET (Dialogfeld) (Legacy)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md).|  
|**Beschreibung**|Die benutzerdefinierte Beschreibung der Aktivität.|  
|**Aktiviert**|Legen Sie auf **"true"** standardmäßig auf die aktivitätsausführung und die Validierung zu aktivieren. Legen Sie auf **"false"** aktivitätsausführung und die Validierung zu deaktivieren. Informationen über die aktivitätsausführung und die Validierung finden Sie unter [Developing Workflow Activities](http://go.microsoft.com/fwlink?LinkID=65024).|  
  
## <a name="adding-child-activities"></a>Hinzufügen von untergeordneten Aktivitäten  
 Sie können untergeordnete Aktivitäten von der Toolbox zu der Aktivität ziehen, die Sie entwerfen. Sie können anschließend jede untergeordnete Aktivität mit dem Eigenschaftenbrowser konfigurieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Entwickeln von Workflowaktivitäten](http://go.microsoft.com/fwlink?LinkID=65024)   
 [Erstellen von benutzerdefinierten Aktivitäten](http://go.microsoft.com/fwlink?LinkID=65021)   
 [Legacyworkflowaktivitäten](../workflow-designer/legacy-workflow-activities.md)   
 [Beispiele für benutzerdefinierte Aktivitäten](http://go.microsoft.com/fwlink?LinkID=65022)   
 [Vorgehensweise: erstellen eine Workflowaktivitätsbibliothek (Vorgängerversion)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md)   
 [Verwenden des Legacyworkflow-Designers](../workflow-designer/using-the-legacy-workflow-designer.md)