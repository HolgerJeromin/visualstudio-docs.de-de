---
title: IDiaStackWalkHelper | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2 interface
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8af7a0f463fc5d2089b374ac881cd0089dce0c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524525"
---
# <a name="idiastackwalkhelper"></a>IDiaStackWalkHelper
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDiaStackWalkHelper](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper).  
  
Erleichtert das Durchlaufen des Stapels, mit der Anwendung debuggen Programmdatenbankdatei (.pdb)-Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
IDiaStackWalkHelper: IUnknown  
  
```  
  
## <a name="methods-in-vtable-order"></a>Methoden in VTable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDiaStackWalkHelper`:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[IDiaStackWalkHelper::get_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-get-registervalue.md)|Ruft den Wert eines Registers.|  
|[IDiaStackWalkHelper::put_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-put-registervalue.md)|Legt den Wert eines Registers.|  
|[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)|Liest einen Block von Daten aus der ausführbaren Datei Image im Arbeitsspeicher.|  
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|Sucht den angegebenen Stapelrahmen für die nächste Funktion Absenderadresse an.|  
|[IDiaStackWalkHelper::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|Sucht den angegebenen Stapelrahmen für eine Absenderadresse an oder in der Nähe der Adresse angegebenen Stapel an.|  
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|Ruft ab den Stapelrahmen, der die angegebene virtuelle Adresse enthält.|  
|[IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|Ruft ab, das Symbol, das die angegebene virtuelle Adresse enthält. **Hinweis:** Symbol muss den Typ aufweisen `SymTagFunctionType` (ein Wert aus der [SymTagEnum-Enumeration](../../debugger/debug-interface-access/symtagenum.md) Enumeration).|  
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|Gibt zurück, der PDATA-Datenblock, der der angegebenen virtuellen Adresse zugeordnet.|  
|[IDiaStackWalkHelper::imageForVA](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|Ruft ab, dass die virtuelle Startadresse einer ausführbaren Datei, wenn eine virtuelle Adresse irgendwo im Speicherbereich der ausführbaren Datei.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird von der DIA-Code zum Abrufen von Informationen zu der ausführbaren Datei zum Erstellen der Liste der Stapelrahmen während der programmausführung aufgerufen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Eine Clientanwendung implementiert diese Schnittstelle, um den Stapel zu durchlaufen, während der Ausführung des Programms zu unterstützen. Eine Instanz dieser Schnittstelle wird zum Übergeben der [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) oder [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) Methoden.  
  
## <a name="requirements"></a>Anforderungen  
 Header: Dia2.h  
  
 Bibliothek: diaguids.lib  
  
 DLL: "MSDIA80.dll"  
  
## <a name="see-also"></a>Siehe auch  
 [Schnittstellen (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [SymTagEnum-Enumeration](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)



