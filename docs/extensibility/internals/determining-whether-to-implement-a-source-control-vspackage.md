---
title: Bestimmt, ob eine Quellcodeverwaltungs-VSPackage implementiert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control packages, about source control packages
ms.assetid: 60b3326e-e7e2-4729-95fc-b682e7ad5c99
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d3bef6030b6a21eeda708a5258c47c9dfdcfc0a3
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497312"
---
# <a name="determine-whether-to-implement-a-source-control-vspackage"></a>Bestimmen Sie, ob ein Quellcodeverwaltungs-VSPackage implementiert.
In diesem Abschnitt werden die Optionen des Quellcodeverwaltungs-Plug-ins und quellcodeverwaltung VSPackages zum Erweitern der quellcodeverwaltung Lösungen und bietet umfassende Richtlinien zum Auswählen eines geeigneten Integration-Pfads.  
  
## <a name="small-source-control-solution-with-limited-resources"></a>Kleine Source Control-Lösung mit begrenzten Ressourcen  
 Wenn Sie nur Ressourcen begrenzte über und können nicht gegen den Aufwand für das Schreiben von ein Quellcode-Verwaltungspaket die threadingverwaltung belastet werden, können Sie die Datenquellen-Steuerelement-Plug-in-API-basierte-Plug-ins erstellen. Auf diese Weise können Sie parallel Quellcodeverwaltungspakete zu arbeiten, und können Sie zwischen den Quellcodeverwaltungs-Plug-ins und -Pakete nach Bedarf wechseln. Weitere Informationen finden Sie unter [Registrierung und Auswahl](../../extensibility/internals/registration-and-selection-source-control-vspackage.md).  
  
## <a name="large-source-control-solution-with-a-rich-feature-set"></a>Große Source Control-Lösung mit einer umfangreichen Featuregruppe  
 Wenn Sie möchten eine Source-Control-Lösung zu implementieren, die eine umfassende quellcodeverwaltungmodell bereitstellt, die mithilfe der Quell-Plug-in-API nicht angemessen erfasst werden, sollten Sie ein Quellcode-Verwaltungspaket als Pfad für die Integration. Dies gilt insbesondere dann, wenn Sie stattdessen das Adapter Quellcodeverwaltungspaket ersetzen (die kommuniziert mit Quellcodeverwaltungs-Plug-ins und bietet eine grundlegende Benutzeroberfläche der quellcodeverwaltung) mit Ihren eigenen, damit Sie die Quellereignisse auf benutzerdefinierte Weise behandeln können. Wenn Sie bereits, zufrieden stellend Quelle Benutzeroberfläche zu steuern, und speichern möchten haben, diesen Effekt in [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], die Paket-Option die Datenquellen-Steuerelement können Sie genau das tun. Das Quellcodeverwaltungspaket ist nicht generisch und dient ausschließlich zur Verwendung mit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 Wenn Sie möchten eine Source-Control-Lösung zu implementieren, die Flexibilität und eine umfangreichere Kontrolle über die Quelle steuernde Logik und Benutzeroberfläche bereitstellt, empfiehlt die Quelle Steuerelement Paket Integration Route. Sie haben folgende Möglichkeiten:  
  
1.  Registrieren Ihrer eigenen quellcodeverwaltung VSPackage (finden Sie unter [Registrierung und Auswahl](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)).  
  
2.  Ersetzen Sie die Standard-quellcodeverwaltung Benutzeroberfläche durch die benutzerdefinierte Benutzeroberfläche (finden Sie unter [benutzerdefinierte Benutzeroberfläche](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)).  
  
3.  Geben Sie die Symbole und Behandeln von Ereignissen der Projektmappen-Explorer-Symbol (finden Sie unter [glyphensteuerung](../../extensibility/internals/glyph-control-source-control-vspackage.md)).  
  
4.  Abfrage bearbeiten und speichern Sie die Abfrage Ereignisse behandeln (finden Sie unter [Abfrage bearbeiten die Abfrage speichern](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines Quellcodeverwaltungs-Plug-in](../../extensibility/internals/creating-a-source-control-plug-in.md)