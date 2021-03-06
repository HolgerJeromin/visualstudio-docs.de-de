---
title: SymTagEnum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SymTagEnum enumeration
ms.assetid: 528a50cf-e13d-46ec-a98c-323d5d047de9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 36dc9b3d9fc15b06c92db27b38d94805c1ce8a25
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
ms.locfileid: "31480861"
---
# <a name="symtagenum"></a>SymTagEnum
Gibt den Typ des Symbols.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
enum SymTagEnum {   
   SymTagNull,  
   SymTagExe,  
   SymTagCompiland,  
   SymTagCompilandDetails,  
   SymTagCompilandEnv,  
   SymTagFunction,  
   SymTagBlock,  
   SymTagData,  
   SymTagAnnotation,  
   SymTagLabel,  
   SymTagPublicSymbol,  
   SymTagUDT,  
   SymTagEnum,  
   SymTagFunctionType,  
   SymTagPointerType,  
   SymTagArrayType,   
   SymTagBaseType,   
   SymTagTypedef,   
   SymTagBaseClass,  
   SymTagFriend,  
   SymTagFunctionArgType,   
   SymTagFuncDebugStart,   
   SymTagFuncDebugEnd,  
   SymTagUsingNamespace,   
   SymTagVTableShape,  
   SymTagVTable,  
   SymTagCustom,  
   SymTagThunk,  
   SymTagCustomType,  
   SymTagManagedType,  
   SymTagDimension,  
   SymTagCallSite,  
   SymTagInlineSite,  
   SymTagBaseInterface,  
   SymTagVectorType,  
   SymTagMatrixType,  
   SymTagHLSLType  
};  
```  
  
## <a name="elements"></a>Elements  
 `SymTagNull`  
 Gibt an, dass das Symbol keinen Typ hat.  
  
 `SymTagExe`  
 Gibt an, dass das Symbol eine .exe-Datei ist. Es Gib nur ein `SymTagExe` Symbol pro Symbolspeicher. Es dient als dem globalen Bereich und keinen lexikalischen ein übergeordnetes Element.  
  
 `SymTagCompiland`  
 Gibt an, die Compiland-Symbol für jede Komponente Kompiliereinheit Symbolspeicher. Für systemeigene Anwendungen `SymTagCompiland` Symbole die Objektdateien verknüpft werden, in der Abbildung entsprechen. Für einige Arten von Bildern für Microsoft Intermediate Language (MSIL) besteht eine Kompiliereinheit pro Klasse zur Verfügung.  
  
 `SymTagCompilandDetails`  
 Gibt an, dass das Symbol erweiterten Attribute von der Kompiliereinheit enthält. Das Abrufen dieser Eigenschaften erfordern Kompiliereinheit Symbole laden.  
  
 `SymTagCompilandEnv`  
 Gibt an, dass das Symbol eine Umgebungszeichenfolge, die für die Kompiliereinheit definiert ist.  
  
 `SymTagFunction`  
 Gibt an, dass das Symbol eine Funktion ist.  
  
 `SymTagBlock`  
 Gibt an, dass das Symbol mit einem geschachtelten Block ist.  
  
 `SymTagData`  
 Gibt an, dass das Symbol Daten ist.  
  
 `SymTagAnnotation`  
 Gibt an, dass das Symbol für eine Anmerkung Code erfolgt. Untergeordnete Elemente dieses Symbols sind Zeichenfolgen mit Konstante Daten (`SymTagData`, `LocIsConstant`, `DataIsConstant`). Die meisten Clients ignorieren dieses Symbol.  
  
 `SymTagLabel`  
 Gibt an, dass das Symbol eine Bezeichnung ist.  
  
 `SymTagPublicSymbol`  
 Gibt an, dass das Symbol ein public-Symbol ist. Für systemeigene Anwendungen wird dieses Symbol das externe COFF-Symbol, verknüpfen das Bild aufgetreten.  
  
 `SymTagUDT`  
 Gibt an, dass das Symbol mit einem benutzerdefinierten Typ (Struktur, Klasse oder Union) ist.  
  
 `SymTagEnum`  
 Gibt an, dass das Symbol eine Enumeration ist.  
  
 `SymTagFunctionType`  
 Gibt an, dass das Symbol eine Signatur Funktionstyp ist.  
  
 `SymTagPointerType`  
 Gibt an, dass das Symbol ein Zeigertyp ist.  
  
 `SymTagArrayType`  
 Gibt an, dass das Symbol ein Arraytyp ist.  
  
 `SymTagBaseType`  
 Gibt an, dass das Symbol ein Basistyp ist.  
  
 `SymTagTypedef`  
 Gibt an, dass das Symbol ist ein `typedef`, d. h. einen Alias für einen anderen Typ.  
  
 `SymTagBaseClass`  
 Gibt an, dass das Symbol eine Basisklasse eines benutzerdefinierten Typs ist.  
  
 `SymTagFriend`  
 Gibt an, dass das Symbol einen "Friend" eines benutzerdefinierten Typs ist.  
  
 `SymTagFunctionArgType`  
 Gibt an, dass das Symbol ein Funktionsargument ist.  
  
 `SymTagFuncDebugStart`  
 Gibt an, dass das Symbol die Endposition des prologcodes für die Funktion ist.  
  
 `SymTagFuncDebugEnd`  
 Gibt an, dass das Symbol die Anfangsposition des epilogcodes der Funktion ist.  
  
 `SymTagUsingNamespace`  
 Gibt an, dass das Symbol ein Namespacename, der im aktuellen Bereich aktiv ist.  
  
 `SymTagVTableShape`  
 Gibt an, dass das Symbol eine Beschreibung der virtuellen Tabelle ist.  
  
 `SymTagVTable`  
 Gibt an, dass das Symbol eine virtuelle Tabelle-Zeiger ist.  
  
 `SymTagCustom`  
 Gibt an, dass das Symbol ein benutzerdefiniertes Symbol ist und wird nicht durch DIA. interpretiert  
  
 `SymTagThunk`  
 Gibt an, dass das Symbol ein Thunk für die Freigabe von Daten zwischen 16 und 32-Bit-Code verwendet wird.  
  
 `SymTagCustomType`  
 Gibt an, dass das Symbol ein Symbol, das benutzerdefinierte Compiler ist.  
  
 `SymTagManagedType`  
 Gibt an, dass das Symbol in Metadaten.  
  
 `SymTagDimension`  
 Gibt an, dass das Symbol ein FORTRAN mehrdimensionales Array ist.  
  
 `SymTagCallSite`  
 Gibt an, dass das Symbol die Aufrufsite darstellt.  
  
 `SymTagInlineSite`  
 Gibt an, dass das Symbol die Inline-Website darstellt.  
  
 `SymTagBaseInterface`  
 Gibt an, dass das Symbol eine Basisschnittstelle ist.  
  
 `SymTagVectorType`  
 Gibt an, dass das Symbol einen Vector-Typ ist.  
  
 `SymTagMatrixType`  
 Gibt an, dass das Symbol einen Matrixtyp ist.  
  
 `SymTagHLSLType`  
 Gibt an, dass das Symbol eine hohe Ebene Shader-Language-Typ ist.  
  
## <a name="remarks"></a>Hinweise  
 Alle Symbole in eine Datei haben ein Identifizierungstag, der das Symbol Typ angibt.  
  
 Die Werte in dieser Enumeration werden zurückgegeben, durch einen Aufruf der [idiasymbol:: Get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) Methode.  
  
 Die Werte in dieser Enumeration werden für die folgenden Methoden zum Begrenzen des Bereichs der Suche auf ein bestimmtes Symbol übergeben:  
  
-   [IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)  
  
-   [IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)  
  
-   [IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)  
  
-   [IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)  
  
-   [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)  
  
-   [IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>Anforderungen  
 Header: cvconst.h  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen und Strukturen](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Lexikalische Hierarchie der Symboltypen](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [Idiasession:: Findsymbolbyaddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)   
 [Idiasession:: Findsymbolbyrva](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)   
 [Idiasession:: Findsymbolbyrvaex](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)   
 [Idiasession:: Findsymbolbytoken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)   
 [Idiasession:: Findsymbolbyva](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)   
 [Idiasession:: Findsymbolbyvaex](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)   
 [Idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)