---
title: 'Vorgehensweise: Verwenden von Textmarkierungen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - using text markers
ms.assetid: 76eed51c-eecb-4579-823e-13df2f0526b9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fdb02ccb4e1b32904e9423a0f851b538144d6f29
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497653"
---
# <a name="how-to-use-text-markers"></a>Gewusst wie: Verwenden von Textmarkierungen
Textmarkierungen angewendet werden, um das Bearbeiten einer <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> Objekt.  
  
## <a name="procedures"></a>Verfahren  
  
### <a name="to-apply-text-markers"></a>Anwenden von Textmarkierungen  
  
1.  Rufen Sie eine Instanz von der <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> Klasse.  
  
    > [!NOTE]
    >  Der Kern-Editor wendet standard Textmarkierungen automatisch für alle Dokumente, die bearbeitet wird, und es sollte nicht erforderlich sein, standard-Text-Kennzeichnungen explizit anwenden.  
  
2.  Erhalten Sie eine Markertyp-ID des Markers, durch den Aufruf interessiert sind der <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> -Methode mit dem `GUID` der textmarkierung Sie zusammenarbeiten möchten.  
  
    > [!NOTE]
    >  Verwenden Sie nicht die `GUID` des VSPackage oder der Dienst, die textmarkierung bereitstellt.  
  
3.  Verwenden, die den Markertyp-ID, durch den Aufruf Abrufen der <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> Methode als Parameter zum Aufrufen der <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> Methode oder der <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> Methode, um eine textmarkierung für eine bestimmte Region des Texts anwenden.  
  
### <a name="to-add-features-to-text-markers"></a>Zum Textmarkierungen hinzufügen  
  
1.  Es möglicherweise wünschenswert, eine textmarkierung, z. B. QuickInfos, einem speziellen Kontext-Menü oder Handler bei besonderen Umständen zusätzliche Funktionen hinzugefügt. Gehen Sie hierzu wie folgt vor:  
  
2.  Erstellen Sie ein Objekt, das die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> Schnittstelle.  
  
3.  Wenn zusätzliche Funktionen wie gewünscht ausfällt, implementieren die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>, und die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced> Schnittstellen für das gleiche Objekt, das implementiert die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> Schnittstelle.  
  
4.  Übergeben der <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> -Schnittstelle, die Sie, an den Aufruf Erstellen der <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> Methode oder der <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> Methode verwendet, um die textmarkierung für eine bestimmte Region Text anzuwenden.  
  
5.  Beim Hinzufügen von Unterstützung für Kontext-Menü zu einer Markierung Textbereich ist es erforderlich, um das Menü zu erstellen.  
  
     Weitere Informationen zum Erstellen finden Sie im Menü ein Kontext [Kontextmenüs](../extensibility/context-menus.md).  
  
6.  Die [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Umgebung Ruft die Methoden der bereitgestellten Schnittstellen, wie z. B. die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetTipText%2A> -Methode, oder die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> Methode je nach Bedarf.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Textmarkierungen mit der legacy-API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Gewusst wie: Hinzufügen von standard-Text-Marker](../extensibility/how-to-add-standard-text-markers.md)   
 [Gewusst wie: Erstellen von benutzerdefinierten Textmarkierungen](../extensibility/how-to-create-custom-text-markers.md)   
 [Gewusst wie: Implementieren von fehlermarker](../extensibility/how-to-implement-error-markers.md)