---
title: 'Prüfliste: Erstellen neuer Projekttypen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], creating new types
- project types, checklist for creating
ms.assetid: 29eb9c3b-1933-4741-aa85-65a33f0825ba
caps.latest.revision: 24
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f73462d32e0b047e0b2427646cfc5a3709c5e78a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509826"
---
# <a name="checklist-creating-new-project-types"></a>Prüfliste: Erstellen neuer Projekttypen
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Checkliste: Erstellen einer neuen Projekttypen](https://docs.microsoft.com/visualstudio/extensibility/internals/checklist-creating-new-project-types).  
  
Sie müssen mehrere Aufgaben aus, um einen neuen Projekttyp erstellen abschließen. Die folgende Checkliste enthält eine Anleitung für diese Aufgaben.  
  
1.  Entwerfen Sie die Funktionalität für den neuen Projekttyp. Weitere Informationen finden Sie unter [Entwurfsentscheidungen bei Projekttypen](../../extensibility/internals/project-type-design-decisions.md).  
  
2.  Bestimmen Sie, welche Editoren für Code und andere Projektelemente verwendet werden. Können Sie Kern- oder standard-Editoren, oder Sie erstellen und Verwenden von projektspezifischen Editoren. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Editoren und Designern](../../extensibility/creating-custom-editors-and-designers.md) und [Vorgehensweise: Öffnen von projektspezifischen Editoren](../../extensibility/how-to-open-project-specific-editors.md).  
  
3.  Bestimmt die Art der Mitgliedschaft Ihrer Projektelemente in müssen der **Klassenansicht** und **Objektkatalog**. Weitere Informationen finden Sie unter [Tools zum Durchsuchen von Symbolen unterstützen](../../extensibility/internals/supporting-symbol-browsing-tools.md).  
  
4.  Leiten Sie neue Klassen basierend auf Entscheidungen, die Sie zuvor für das Projekt und Projektelemente vorgenommen.  
  
5.  Schreiben Sie Code für die folgenden Komponenten des Projekt-Typ:  
  
    -   Projektfactory, um das Erstellen neuer Projekte, und Öffnen von vorhandenen Projekten zu verwalten. Weitere Informationen finden Sie unter [erstellen Projekt Instanzen von mithilfe von Projektfactorys](../../extensibility/internals/creating-project-instances-by-using-project-factories.md).  
  
    -   Teamprojekthierarchie und Behandlung von Befehlen. Weitere Informationen finden Sie unter [nicht im Build: Verwenden von HierUtil7 Projektklassen implementieren Sie eine Projekt-Typ (C++)](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346), [Elemente eines Projektmodells](../../extensibility/internals/elements-of-a-project-model.md), [Hauptkomponenten eines Projektmodells](../../extensibility/internals/project-model-core-components.md)und [MenuCommands im Vergleich. OleMenuCommands](../../misc/menucommands-vs-olemenucommands.md).  
  
    -   Verwaltung, einschließlich des Hinzufügens von das Projekt für die Elemente der **neues Projekt** Dialogfeld. Weitere Informationen finden Sie unter [Hinzufügen von Projekt- und Projektelementvorlagen](../../extensibility/internals/adding-project-and-project-item-templates.md) und [Registrieren von Projekt- und Elementvorlagen](../../extensibility/internals/registering-project-and-item-templates.md).  
  
    -   Die Dauerhaftigkeit des Projektzustands und einzelne Elemente. Weitere Informationen finden Sie unter [öffnen und Speichern von Projektelementen](../../extensibility/internals/opening-and-saving-project-items.md). Persistenz der Informationen zur Lösung finden Sie unter [Lösungen](../../extensibility/internals/solutions.md).  
  
    -   Unabhängige Eigenschaften im Eigenschaftenfenster angezeigt. Weitere Informationen finden Sie unter [Erweitern von Eigenschaften](../../extensibility/internals/extending-properties.md).  
  
    -   Projizieren Sie Konfigurationseigenschaften an, wie in den Eigenschaftenseiten, um die konfigurationsabhängigen Eigenschaften implementiert. Weitere Informationen finden Sie unter [Konfigurationsoptionen verwalten](../../extensibility/internals/managing-configuration-options.md).  
  
    -   Auflisten von Ausgaben für die Bereitstellung aus. Weitere Informationen finden Sie unter [Projektkonfiguration für die Ausgabe](../../extensibility/internals/project-configuration-for-output.md).  
  
    -   Projekt Startdienste. Weitere Informationen finden Sie unter [Elemente eines Projektmodells](../../extensibility/internals/elements-of-a-project-model.md) und [Hauptkomponenten eines Projektmodells](../../extensibility/internals/project-model-core-components.md).  
  
    -   Objekte oder von abgeleiteten Klassen `IDispatch`, für die Automatisierung verfügbar.  
  
    -   XML-Command Table (.vsct)-Dateien. Weitere Informationen finden Sie unter [Visual Studio Command Table (. VSCT) Dateien](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
6.  Testen Sie, Debuggen Sie und starten Sie die Art Ihres Projekts.  
  
7.  Zeigen Sie Ihr Projekt in der **Projekt** Registerkarte die **Verweis hinzufügen** Dialogfeld durch Festlegen von `VARIANT_TRUE` als Wert für `VSHPROPID_ShowProjInSolutionPage`. Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> und <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>.  
  
8.  Erstellen Sie die Microsoft Installer (MSI)-Datei für die Installation von Ihre VSPackages. Weitere Informationen finden Sie unter [Installieren von VSPackages mit Windows Installer](../../extensibility/internals/installing-vspackages-with-windows-installer.md), [Registrieren eines Projekttyps](../../extensibility/internals/registering-a-project-type.md), und [VSPackages](../../extensibility/internals/vspackages.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchien in Visual Studio](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [Gründe für das Erstellen von Projekttypen](../../extensibility/internals/when-to-create-project-types.md)   
 [Erstellen von Projekttypen](../../extensibility/internals/creating-project-types.md)

