---
title: 'DA0011: Speicherintensive CompareTo-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.DA0011
- vs.performance.rules.DAExpensiveCompareTo
- vs.performance.11
- vs.performance.rules.DA0011
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9958e9ec729591aa89c97d4f1d23a819e7b7eeb6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524208"
---
# <a name="da0011-expensive-compareto"></a>DA0011: Speicherintensive CompareTo-Funktionen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Dokumentation für Visual Studio 2017 finden Sie unter [DA0011: speicherintensive CompareTo-Funktionen](https://docs.microsoft.com/visualstudio/profiling/da0011-expensive-compareto) auf docs.microsoft.com.  
  
|||  
|-|-|  
|Regel-ID|DA0011|  
|Kategorie|.NET Framework-Verwendung|  
|Profilerstellungsmethoden|Sampling<br /><br /> .NET-Arbeitsspeicher|  
|Meldung|CompareTo-Funktionen dürfen nicht speicherintensiv sein und keinen Speicher belegen. Reduzieren Sie daher, wenn möglich, die Komplexität der CompareTo-Funktionen.|  
|Regeltyp|Warnung|  
  
## <a name="cause"></a>Ursache  
 Die CompareTo-Methode des Typs ist aufwändig oder belegt Arbeitsspeicher.  
  
## <a name="rule-description"></a>Regelbeschreibung  
 CompareTo-Methoden sollten effizient sein und keinen Arbeitsspeicher zuordnen.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Verringern Sie die Komplexität der CompareTo-Methode.

