---
title: SccIsMultiCheckoutEnabled-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccIsMultiCheckoutEnabled
helpviewer_keywords:
- SccIsMultiCheckoutEnabled function
ms.assetid: 6721639d-e475-4766-81b5-ee40a280fc70
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 11bd525d90f6c593c7a78de5734fa2b2e718c9db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523466"
---
# <a name="sccismulticheckoutenabled-function"></a>SccIsMultiCheckoutEnabled-Funktion
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [SccIsMultiCheckoutEnabled-Funktion](https://docs.microsoft.com/visualstudio/extensibility/sccismulticheckoutenabled-function).  
  
Diese Funktion überprüft, ob das Quellcodeverwaltungs-Plug-in Mehrfaches Auschecken in einer Datei ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
SCCRTN SccIsMultiCheckoutEnabled(  
   LPVOID pContext,  
   LPBOOL pbMultiCheckout  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 "pContext"  
 [in] Datenquellen-Steuerelement-Plug-in Context-Struktur.  
  
 pbMultiCheckout  
 [out] Gibt an, ob es sich bei Mehrfaches Auschecken für dieses Projekt (ungleich NULL bedeutet, dass Mehrfaches Auschecken unterstützt werden) aktiviert sind.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Source-Steuerelement-Plug-in-Implementierung dieser Funktion muss einen der folgenden Werte zurückgeben:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|SCC_OK|Die Überprüfung war erfolgreich.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Nicht spezifischen Fehler.|  
  
## <a name="remarks"></a>Hinweise  
 Die IDE macht zwei prüft, ob Dateien von mehr als einem Benutzer ausgecheckt werden können. Zunächst muss das Quellcodeverwaltungssystem Mehrfaches Auschecken unterstützen. Das Quellcodeverwaltungs-Plug-in kann diese Funktion während der Initialisierung geben, indem Sie die `SCC_CAP_MULTICHECKOUT`. Danach, wie einer zweiten Überprüfung, ruft die IDE dieser Funktion können Sie bestimmen, ob das aktuelle Projekt Mehrfaches Auschecken unterstützt. Wenn Mehrfaches Auschecken für das ausgewählte Projekt unterstützt werden, die Plug-in-gibt ein Erfolg, code, und legt sie fest `pbMultiCheckout` zu ungleich Null (`TRUE`) oder `FALSE`.  
  
## <a name="see-also"></a>Siehe auch  
 [API-Funktionen von Quellcodeverwaltungs-Plug-Ins](../extensibility/source-control-plug-in-api-functions.md)

