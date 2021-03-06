---
title: Enumeratoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e555ca317dea79d1fe3b856a7c449d01f0b792af
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39636225"
---
# <a name="enumerators"></a>Enumeratoren
Dieser Abschnitt enthält die Datentypen der Enumerator in der Quelle Steuerelement-Plug-in-API, die das Quellcodeverwaltungs-Plug-in zu kennen müssen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Befehlscode](../extensibility/command-code-enumerator.md)  
 Listet die Optionen für die [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) und [SccPopulateList](../extensibility/sccpopulatelist-function.md) Funktionen.  
  
 [Nachricht](../extensibility/message-enumerator.md)  
 Listet Flags, die zum Drucken Rückrufs [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).  
  
 [Datei-Statuscode](../extensibility/file-status-code-enumerator.md)  
 Enthält die benannten Konstante Werte, die den Status einer Datei unter quellcodeverwaltung angeben.  
  
 [Directory-Statuscode](../extensibility/directory-status-code-enumerator.md)  
 Enthält die benannten Konstante Werte, die den Status eines Verzeichnisses in der quellcodeverwaltung angeben.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Erstellen eines Quellcodeverwaltungs-Plug-in](../extensibility/internals/creating-a-source-control-plug-in.md)  
 Die Source-Steuerelement-Plug-in SDK definiert und beschreibt die Ressourcen enthalten.  
  
 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)  
 Fordert den Benutzer für die erweiterten Optionen für den angegebenen Befehl.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Untersucht die Liste der Dateien für ihren aktuellen Status an. Darüber hinaus verwendet der `pfnPopulate` Funktion, um den Aufrufer darüber zu benachrichtigen, wenn eine Datei nicht die Kriterien für entspricht der `nCommand`.  
  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Beschreibt die Callback-Funktion, mit dem [SccOpenProject](../extensibility/sccopenproject-function.md) werden die Nachrichten über das Quellcodeverwaltungs-Plug-in über die IDE angezeigt.  
  
 [Quellcodeverwaltungs-Plug-ins](../extensibility/source-control-plug-ins.md)  
 Enthält eine vollständige Liste aller Elemente in der Quelle-Plug-in-API.