---
title: Entfernen von Informationen der Quellcodeverwaltung aus. Proj und. Sln-Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7c6709d7808eba229455805ecb2b4a8d0c8af525
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524270"
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>Entfernen von Informationen der Quellcodeverwaltung aus PROJ- und SLN-Dateien
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [zum Entfernen von Informationen der Quellcodeverwaltung aus. Proj und. Sln-Dateien](https://docs.microsoft.com/visualstudio/extensibility/internals/removal-of-source-control-information-from-dot-proj-and-dot-sln-files).  
  
In Version 1.2 von die Source-Plug-in-API SCC werden die Informationen in einem MSSCCPRJ gespeichert. SCC-Datei. Der Vorteil der MSSCCPRJ. SCC-Datei ist, dass die SCC-Informationen ist nicht im Quellmodell - gesteuert, wie in proj- und sln-Dateien.  
  
## <a name="version-12-changes"></a>Versionsänderungen 1.2  
 Im Quellcodeverwaltungs-Plug-ins, die auf die Datenquellen-Steuerelement-Plug-in API-Version 1.1 basieren, werden die Informationen zur Versionskontrolle in den Projektdateien (proj) und Projektmappendateien (.sln) gespeichert. Speicherort der Datenbank, der die Informationen der quellcodeverwaltung wird durch die AuxPath angegeben, und bestimmte Position innerhalb der Datenbank durch Projektname angegeben ist. Dieses Verhalten kann nach dem Branch, Verzweigung oder Kopiervorgänge Probleme verursachen, da der Projektname in der Regel ungültige nach jedem dieser Vorgänge wären.  
  
 In der Quelle-Plug-in-API Version 1.1 der IDE verwendet ~ SAK-Dateien zu erkennen, ob ein plug-in die MSSCCPRJ unterstützt. SCC-Methode zum Speichern von Informationen der quellcodeverwaltung. Die Source-Plug-in-API Version 1.2 stellt eine neue Funktion zum Erkennen der Unterstützung für MSSCCPRJ bereit. SCC-Datei ohne Verwendung einer ~ SAK-Datei. Weitere Informationen finden Sie unter [Beseitigung von ~ SAK-Dateien](../../extensibility/internals/elimination-of-tilde-sak-files.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Neuigkeiten in API-Version 1.2 des Quellcodeverwaltungs-Plug-Ins](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

