---
title: Kontextoperator (C++) | Microsoft-Dokumentation
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
- vs.debug.operators
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- expressions [C++], native debugger
- evaluation
- format specifiers, expressions
- context operator, in expressions
- debugging [C++], expressions
- native expression evaluator
ms.assetid: 73cc9afe-f4a4-474e-bb89-5a33fb5e570c
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8a3c033175b1ee7fcd0d7fcbaeae5d64a928289
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524913"
---
# <a name="context-operator-c"></a>Kontextoperator (C++)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Context Operator (C++)](https://docs.microsoft.com/visualstudio/debugger/context-operator-cpp).  
  
Sie können den Kontextoperator in C++ zur Kennzeichnung von Haltepunktpositionen, Variablennamen oder Ausdrücken verwenden. Der Kontextoperator eignet sich für die Angabe eines Namens außerhalb des Gültigkeitsbereichs, der andernfalls durch einen lokalen Namen verborgen würde.  
  
##  <a name="BKMK_Using_context_operators_to_specify_a_symbol"></a> Syntax  
 Es gibt zwei Methoden zum Angeben von Kontext:  
  
1.  {,,[*module*] } *expression*  
  
     Die Klammern müssen zwei Kommas und den Modulnamen (ausführbare Datei oder DLL) oder den vollständigen Pfad enthalten.  
  
     Um z. B. in der `SomeFunction` -Funktion von EXAMPLE.dll einen Haltepunkt festlegen, gehen Sie wie folgt vor:  
  
    ```cpp  
    {,,EXAMPLE.dll}SomeFunction  
    ```  
  
2.  *module*!*expression*  
  
    ```cpp  
    EXAMPLE.dll!SomeFunction  
    ```  
  
-   *module* ist der Name eines Moduls. Sie können einen vollständigen Pfad verwenden, um zwischen Modulen mit demselben Namen zu unterscheiden.  
  
     Wenn der *module* -Pfad ein Komma, ein eingebettetes Leerzeichen oder eine geschweifte Klammer enthält, müssen Sie den Pfad in doppelte Anführungszeichen einschließen, damit die Zeichenfolge vom Kontextparser richtig erkannt wird. Einfache Anführungszeichen werden als Teil eines Windows-Dateinamens betrachtet. Daher sollten stets doppelte Anführungszeichen verwendet werden. Ein auf ein Objekt angewendeter  
  
    ```cpp  
    {,,"a long, long, library name.dll"} g_Var  
    ```  
  
-   *expression* ist ein beliebiger gültiger C++-Ausdruck, der zu einem gültigen Ziel, z. B. einem Funktionsnamen, einem Variablennamen oder einer Zeigeradresse in *module*aufgelöst wird.  
  
 Wenn die Ausdrucksauswertung in einem Ausdruck auf ein Symbol trifft, wird in der folgenden Reihenfolge danach gesucht:  
  
1.  Beginnend mit dem aktuellen Block (in geschweifte Klammern eingeschlossene Anweisungsreihe) vom lexikalischen Gültigkeitsbereich nach außen und weiter zum äußeren, umschließenden Block. Der aktuelle Block entspricht dem Code mit der aktuellen Position (der Adresse des Anweisungszeigers).  
  
2.  Gültigkeitsbereich der Funktion. Die aktuelle Funktion.  
  
3.  Gültigkeitsbereich der Klasse, sofern sich die aktuelle Position innerhalb einer C++-Memberfunktion befindet. Der Klassengültigkeitsbereich umfasst alle Basisklassen. Von der Ausdrucksauswertung werden die normalen Dominanzregeln verwendet.  
  
4.  Globale Symbole im aktuellen Modul.  
  
5.  Öffentliche Symbole im aktuellen Programm.





