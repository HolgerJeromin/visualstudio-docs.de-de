---
title: Laufzeitdetails für die Datenquelle | Microsoft-Dokumentation
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
- source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ca2d6830a9feb61c088274761995eeb227b1d661
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47520908"
---
# <a name="source-control-runtime-details"></a>Laufzeitdetails für die Quellcodeverwaltung
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Laufzeitdetails für die Quelle](https://docs.microsoft.com/visualstudio/extensibility/internals/source-control-runtime-details).  
  
Ein Projekt wird zur quellcodeverwaltung hinzugefügt werden, wenn der Benutzer eine Datei im Projekt zur quellcodeverwaltung oder über eines Automatisierungscontrollers, wie z. B. einen Assistenten hinzufügt. Ein Projekt ist nicht für sich selbst festlegen, dass dieser unter quellcodeverwaltung; Datenquellen-Steuerelement unterstützt, sondern muss, manuell hinzugefügt werden.  
  
## <a name="registering-with-a-source-control-package"></a>Registrieren mit einem Quellcode-Verwaltungspaket  
 Wenn eine Datei in Ihrem Projekt zur quellcodeverwaltung hinzugefügt wird, wird die Umgebung ruft <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> vier opake Zeichenfolgen bereit, die durch das Quellcode-Verwaltungssystem als Cookies verwendet werden. Store diese Zeichenfolgen in der Projektdatei an. Diese Zeichenfolgen übergeben werden sollte, die Quellcode-Verwaltungsstub (der Visual Studio-Komponente, die Quellcodeverwaltungspakete verwaltet) beim Start des Projekttyps durch Aufrufen von <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>. Dies wiederum den entsprechenden Quellcode-Verwaltungspaket lädt und leitet den Anruf an seine Implementierung von `IVsSccManager2::RegisterSccProject`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>   
 [Unterstützen der Quellcodeverwaltung](../../extensibility/internals/supporting-source-control.md)
