---
title: Unterstützung von Tools zum Durchsuchen des Symbols | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- symbols, symbol-browsing tools
- browsers, symbol browsers
- symbol-browsing tools
- libraries
- IVsLibrary2 interface, symbol-browsing tools
- IVsSimpleLibrary2 interface, symbol-browsing tools
- symbol-browsing tools, library manager
- symbols
- libraries, symbol-browsing tools
ms.assetid: 70d8c9e5-4b0b-4a69-b3b3-90f36debe880
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 08185f64310da610253dc35e69323b17ab0177fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134585"
---
# <a name="supporting-symbol-browsing-tools"></a>Unterstützung von Tools zum Durchsuchen des Symbols
**Objektkatalog**, **Klassenansicht**, **Aufrufbrowser** und **Ergebnisse der Symbolsuche** Tools bieten Funktionen in Visual Studio zum Durchsuchen Symbol. Diese Tools hierarchische Strukturansichten der Symbole angezeigt, und zeigen die Beziehungen zwischen den Symbolen in der Struktur. Die Symbole können Namespaces, Objekte, Klassen, Klassenmembern und anderen Language-Elemente in verschiedenen Komponenten darstellen. Zu den Komponenten zählen Visual Studio-Projekte, die externe [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] Komponenten und Typbibliotheken (TLB-Datei). Weitere Informationen finden Sie unter [Anzeigen der Codestruktur](../../ide/viewing-the-structure-of-code.md).  
  
## <a name="symbol-browsing-libraries"></a>Symbol zum Durchsuchen von Bibliotheken  
 Als eine Ausführender Sprache können Sie die Visual Studio-Symbol durchsuchen-Funktionen erweitern, durch das Erstellen von Bibliotheken, die die Symbole in Ihren Komponenten nachverfolgen und die Listen der Symbole für die Visual Studio-Objekt-Manager über eine Reihe von Schnittstellen bereitstellen. Eine Bibliothek wird beschrieben, durch die <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2> Schnittstelle. Der Visual Studio-Objekt-Manager reagiert auf Anforderungen für neue Daten von den Tools zum Durchsuchen des Symbols durch Abrufen von Daten aus den Bibliotheken und Organisieren es. Anschließend füllt, oder aktualisiert die Tools mit der angeforderten Daten. Um einen Verweis auf die Visual Studio-Objekt-Manager erhalten <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>, übergeben die <xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> Dienst-ID, die `GetService` Methode.  
  
 Jede Bibliothek muss mit den Visual Studio-Objekt-Manager registrieren, und die Informationen zu allen Bibliotheken zu sammeln. Um eine Bibliothek zu registrieren, rufen Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> Methode. Je nachdem, welches Tool die Anforderung initiiert wird der Objekt-Manager von Visual Studio findet die entsprechende Bibliothek und Daten anfordert. Die Daten zwischen den Bibliotheken durchläuft und die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] -Objekt-Manager in Listen der Symbole beschrieben, die von der <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> Schnittstelle.  
  
 Die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] -Objekt-Manager ist verantwortlich für die Aktualisierung in regelmäßigen Abständen von Tools zum Durchsuchen des Symbols entsprechend die aktuellen Daten in den Bibliotheken enthalten.  
  
 Das folgende Diagramm enthält ein Beispiel der Schlüsselelemente des Anforderungen/Exchange von Daten zwischen einer Bibliothek und der Visual Studio-Objekt-Manager. Die Schnittstellen im Diagramm sind Teil einer Anwendung mit verwaltetem Code.  
  
 ![Datenfluss zwischen einer Bibliothek und der Objekt-Manager](../../extensibility/internals/media/callbrowserdiagram.gif "CallBrowserDiagram")  
  
 Um die Liste der Symbole von dem Visual Studio-Objekt-Manager bereitzustellen, müssen Sie zuerst die Bibliothek mit den Visual Studio-Objekt-Manager registrieren, durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> Methode. Nachdem die Bibliothek registriert ist, fordert der Objekt-Manager für Visual Studio bestimmte Informationen zu den Funktionen der Bibliothek. Angenommen, es fordert die Bibliotheksflags und unterstützt Kategorien durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetLibFlags2%2A> und <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetSupportedCategoryFields2%2A> Methoden. Zu einem späteren Zeitpunkt bei einem der Tools aus dieser Bibliothek datenanforderungen der Objekt-Manager fordert die obersten Ebene Liste von Symbolen durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleLibrary2.GetList2%2A> Methode. In der Antwort, die Bibliothek stellt eine Liste von Symbolen und macht es für den Visual Studio-Objekt-Manager über die <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> Schnittstelle. Die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] -Objekt-Manager bestimmt, wie viele Elemente in der Liste durch den Aufruf werden die <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetItemCount%2A> Methode. Alle folgenden Anforderungen beziehen sich auf ein bestimmtes Element in der Liste, und geben Sie die Index-Artikelnummer in jeder Anforderung. Der Visual Studio-Objekt-Manager wird fortgesetzt, die auf den Typ, der Zugriff auf und andere Eigenschaften des Elements durch den Aufruf Erfassen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetCategoryField2%2A> Methode.  
  
 Bestimmt den Namen des Elements durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetTextWithOwnership%2A> Methode und fordert Sie das Symbol Informationen durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetDisplayData%2A> Methode. Das Symbol wird angezeigt, auf der linken Seite des Elementnamens dargestellt und geben den Typ des Elements, der Zugriff auf und andere Eigenschaften.  
  
 Die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] -Objekt Manager Ruft die <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetExpandable3%2A> Methode, um zu bestimmen, ob ein bestimmtes Listenelement erweiterbar und untergeordnete Elemente verfügt. Wenn UI eine Anforderung zum Erweitern eines Elements sendet, fordert der Objekt-Manager die untergeordnete Liste der Symbole durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetList2%2A> Methode. Der Prozess wird mit verschiedenen Teilen der Struktur, die bei Bedarf erstellt wird.  
  
> [!NOTE]
>  Um ein Symbol-Anbieter von systemeigenem Code zu implementieren, verwenden die <xref:Microsoft.VisualStudio.Shell.Interop.IVsLibrary2> und <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectList2> Schnittstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Registrieren Sie eine Bibliothek mit dem Objekt-Manager](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [Vorgehensweise: Listen von Symbolen, die von der Bibliothek bereitgestellt, den Objekt-Manager verfügbar machen](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)   
 [Gewusst wie: Identifizieren von Symbolen in einer Bibliothek](../../extensibility/internals/how-to-identify-symbols-in-a-library.md)