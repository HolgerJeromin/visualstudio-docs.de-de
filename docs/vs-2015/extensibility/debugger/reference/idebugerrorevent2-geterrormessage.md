---
title: IDebugErrorEvent2::GetErrorMessage | Microsoft-Dokumentation
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
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 516119fbe944b0aeeaa50516cf76a7745a5343f2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47521179"
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDebugErrorEvent2::GetErrorMessage](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugerrorevent2-geterrormessage).  
  
Gibt zurück, anhand derer der Erstellung der eine lesbare Fehlermeldung aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT GetErrorMessage(  
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrErrorFormat,  
   HRESULT*     hrErrorReason,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetErrorMessage(  
   out enum_MESSAGETYPE   pMessageType,  
   out string             pbstrErrorFormat,  
   out int                phrErrorReason,  
   out uint               pdwType,  
   out string             pbstrHelpFileName,  
   out uint               pdwHelpId  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pMessageType`  
 [out] Gibt einen Wert aus der [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) Enumeration, die den Typ der Nachricht beschreibt.  
  
 `pbstrErrorFormat`  
 [out] Das Format der die endgültige Nachricht an den Benutzer (Details finden Sie unter "Hinweise").  
  
 `hrErrorReason`  
 [out] Der Fehlercode der Nachricht geht.  
  
 `pdwType`  
 [out] Schweregrad des Fehlers (verwenden Sie für Konstanten MB_XXX `MessageBox`, z. B. `MB_EXCLAMATION` oder `MB_WARNING`).  
  
 `pbstrHelpFileName`  
 [out] Der Pfad zu einer Hilfedatei (festgelegt auf einen null-Wert, wenn keine Hilfedatei vorhanden ist).  
  
 `pdwHelpId`  
 [out] Die ID des Hilfethemas zum Anzeigen der (auf 0, wenn kein Hilfethema festgelegt).  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Fehlermeldung, die ungefähr folgendermaßen formatiert werden sollen `"What I was doing.  %1"`. Die `"%1"` würde dann vom Aufrufer mit der Fehlermeldung, abgeleitet aus dem Fehlercode ersetzt (der im zurückgegeben `hrErrorReason`). Die `pMessageType` -Parameter weist den Aufrufer wie die letzte Fehlermeldung angezeigt werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)

