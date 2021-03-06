---
title: Grafikzustand | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.statewindow
ms.assetid: 97e7757e-c372-4626-8149-99a81367a0e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b45e5d922a5f2ed5a2ba15086c708c734d25e95
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476379"
---
# <a name="graphics-state"></a>Grafikzustand
Im Statusfenster der Visual Studio-Grafikdiagnose sehen Sie den Grafikstatus, der zum Zeitpunkt des aktuellen Ereignisses aktiv ist, wie z. B. bei einem Zeichnen-Befehl.  
  
## <a name="understanding-the-state-window"></a>Grundlegendes zum Statusfenster  
 Das Statusfenster fasst die Zustände zusammen, die sich auf das Rendering auswirken, und stellt sie an einem zentralen Ort hierarchisch dar. Abhängig von der Direct3D-Version, die Ihre App verwendet, können sich die im Statusfenster angezeigten Informationen unterscheiden.  
  
### <a name="state-views"></a>Statusansichten  
 Sie können die Statustabelle auf verschiedene Art und Weise anzeigen:  
  
|Ansicht|Beschreibung|  
|----------|-----------------|  
|API-Eingabestatusansicht|Diese Ansicht zeigt den Status in einem ähnlichen Layout wie die Direct3D-Objekte an, die den Status bilden.|  
|Logische Eingabestatusansicht|Diese Ansicht stellt den Status in einer logischen Ansicht dar, die nicht das Layout der Direct3D-Objekte widerspiegelt, die den Status bilden.|  
|Angeheftete Statusansicht|Anstelle einer Hierarchie stellt die angeheftete Statusansicht angeheftete Statuselemente in einer flachen Liste mit vollqualifizierten Namen dar. In dieser Ansicht können zahlreiche Statuselemente aus verschiedenen Statusbündeln in nur wenigen Zeilen angezeigt werden.|  
  
##### <a name="to-change-the-state-view"></a>So ändern Sie die Statusansicht  
  
-   Klicken Sie im Statusfenster in der oberen linken Ecke direkt unterhalb der Titelleiste auf die Schaltfläche, die dem gewünschten Statusansichtsstil entspricht.  
  
    -   **API-eingabestatusansicht anzeigen**  
  
    -   **Logische Statusansicht anzeigen**  
  
    -   **Angeheftete Statusansicht anzeigen**  
  
> [!IMPORTANT]
>  Müssen Sie anheften, Status in der **API anzeigen Eingabe Zustand** oder **logischen Status anzeigen** Ansichten, damit er in angezeigt werden die **angeheftete Statusansicht anzeigen**.  
  
### <a name="state-table-format"></a>Format der Statustabelle  
 Das Statusfenster enthält mehrere Spalten mit Informationen.  
  
|Spalte|Beschreibung|  
|------------|-----------------|  
|name|Der Name des Statuselements. Wenn dieses Element Statusbündel darstellt, kann das Element erweitert werden, um es anzuzeigen.<br /><br /> In der **API Eingabe Statusansicht** und **logischen Statusansicht** angegeben, um die hierarchische Beziehung zwischen den Zuständen an eingerückt werden.<br /><br /> In der **angeheftete Statusansicht** Zustand befindet, vollständig qualifizierte Namen in einer flachen Liste angezeigt werden.|  
|Wert|Der Wert des Statuselements.|  
|Typ|Der Typ des Statuselements.|  
  
### <a name="changed-state"></a>Geänderter Status  
 Der Grafikstatus ändert sich in der Regel inkrementell zwischen nachfolgende Zeichnen-Befehlen, und viele Arten von Renderingprobleme treten auf, wenn der Status nicht ordnungsgemäß geändert wird. Um Sie dabei zu unterstützen, zu ermitteln, welcher Status sich seit dem letzten Zeichnen-Befehl geändert hat, wird ein geänderter Status durch ein rotes Sternchensymbol (*) markiert. Dies bezieht sich nicht nur auf den Status selbst, sondern auch auf den übergeordneten Status, sodass Sie Änderungen sofort auf der obersten Ebene erkennen und dann zu den Details vordringen können.  
  
### <a name="pinning-state"></a>Angehefteter Status  
 Da viele Apps ähnliche Objekte nacheinander rendern und dabei einen Satz bekannter Status ändern, ist es manchmal sinnvoll, die veränderlichen Status anzuheften, sodass Sie die Änderungen von Zeichen-Befehl zu Zeichen-Befehl sehen können.  
  
 Dies kann auch nützlich sein, wenn Sie die Änderung eines bestimmten Zustands als Ursache eines Problems ermittelt haben.  
  
##### <a name="to-pin-state-in-place"></a>So heften Sie einen Status an  
  
1.  Suchen Sie den gewünschten Status im Statusfenster. Sie müssen möglicherweise einen Status auf höherer Ebene erweitern, um die Details zum gewünschten Status anzuzeigen.  
  
2.  Platzieren Sie den Cursor auf dem gewünschten Status. Eine Pinsymbol wird auf der linken Seite des Statuselements angezeigt.  
  
3.  Klicken Sie auf das Pinsymbol, um das Statuselement anzuheften.