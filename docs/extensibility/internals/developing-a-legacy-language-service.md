---
title: Entwickeln eines Legacysprachdiensts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- vs.vsip.LangServWiz.langtoks
- vs.vsip.LangServWiz.welcome
- vs.vsip.LangServWiz.langSpec
- vs.vsip.LangServWiz.langInfo
- vs.vsip.LangServWiz.langServOpts
helpviewer_keywords:
- language services, developing
ms.assetid: 6151ba88-c1c3-41de-a1cc-668f494d48d1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d92c07742dcc4433aa96071d655f58d938a1f80
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497829"
---
# <a name="develop-a-legacy-language-service"></a>Entwickeln eines Datendiensts legacysprache
Dieser Abschnitt enthält Links zu Themen, mit denen Sie erstellen einen legacy-Sprachdienst.  
  
 Legacy-Sprachdienste werden als Teil eines VSPackage implementiert, aber die neuere Methode zum Implementieren von Sprache-Service-Features ist die Verwendung von MEF-Erweiterungen. Um mehr über die neue Methode zum Implementieren von eines Sprachdiensts zu suchen, finden Sie unter [, Editoren und Sprachen Webdiensterweiterungen](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Es wird empfohlen, dass Sie nun den neuen Editor API so bald wie möglich zu verwenden. Dies verbessert die Leistung des Sprachdiensts und können Sie neue Features im Editor nutzen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Modell eines Diensts der legacysprache](../../extensibility/internals/model-of-a-legacy-language-service.md)  
 Bietet ein Modell eines Diensts minimale Sprache für die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] -Kern-Editor. Sie können dieses Modell als Leitfaden verwenden, für das Erstellen eigener Sprachdiensts.  
  
 [Dienstschnittstellen legacysprache](../../extensibility/internals/legacy-language-service-interfaces.md)  
 Beschreibt die Objekte erforderlich, um einen Sprachdienst zu implementieren, und enthält eine Liste von zusätzlichen Objekten, die Sie verwenden können, um syntaxhervorhebung, Methodendaten und andere Funktionen bereitzustellen.  
  
 [Abfangen von Befehlen von legacysprachdiensten legacy](../../extensibility/internals/intercepting-legacy-language-service-commands.md)  
 Beschreibt, wie zum Einfügen von eines Befehlsfilter in Ihren Sprachdienst, zum Abfangen von Befehlen, die andernfalls von die Textansicht behandelt würden.  
  
 [Registrieren von Diensten legacysprache](../../extensibility/internals/registering-a-legacy-language-service2.md)  
 Enthält Informationen zum Registrieren des Sprachdiensts mit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Sprachdienstunterstützung für das Debuggen](../../extensibility/internals/language-service-support-for-debugging.md)  
 Beschreibt, wie ein Sprachdienst Funktionen zur Unterstützung von eines Debuggers bereitstellen kann.  
  
 [Prüfliste: Erstellen einer legacysprachdiensten](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)  
 Enthält schrittweise Anleitungen zum Erstellen und die Integration von einem Sprachdienst für die Kern-Editor.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Syntaxfarben in einem legacysprachdiensten](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Erläutert, wie syntaxhervorhebung in den Sprachdienst zu implementieren.  
  
 [Anweisungsvervollständigung in einem legacy-Sprachdienst](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)  
 Erläutert die Anweisungsvervollständigung, den Prozess mit dem ein Sprachdienst hilft Benutzern, die abgeschlossen wird, ein Programmiersprachen-Schlüsselwort oder das Element, die sie eingeben gestartet wurden.  
  
 [ParameterInfo in einer legacysprachdiensten](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)  
 Beschreibt, wie um methodentipps für überladene Funktionen und Methoden bereitzustellen.  
  
 [Vorgehensweise: Bereitstellen von ausgeblendetem Text in einem älteren Sprachdienst zu unterstützen](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)  
 Erläutert den Zweck eines Bereichs von ausgeblendetem Text, und enthält Anweisungen dazu, wie Sie einen Bereich des ausgeblendeten Textes zu implementieren.  
  
 [Gewusst wie: Bereitstellen von Unterstützung für erweiterte Gliederungen in einem legacy-Sprachdienst](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)  
 Erläutert die zwei Optionen, die Gliederung für Ihre Sprache zu unterstützen, erweitert die *reduzieren auf Definitionen* Befehl.