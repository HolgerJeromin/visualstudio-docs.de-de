---
title: 'Vorgehensweise: Anwenden eines Shaders auf ein 3D-Modell | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 277711a0dd2a106c8770b2b7d720666589e65d86
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47520861"
---
# <a name="how-to-apply-a-shader-to-a-3-d-model"></a>Gewusst wie: Anwenden eines Shaders auf ein 3D-Modell
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Vorgehensweise: Anwenden eines Shaders auf ein 3D-Modell](https://docs.microsoft.com/visualstudio/designers/how-to-apply-a-shader-to-a-3-d-model).  
  
In diesem Dokument wird gezeigt, wie der Modell-Editor verwendet wird, um einen Directed Graph Shader Language (DGSL)-Shader auf ein 3-D-Modell anzuwenden.  
  
 In diesem Dokument wird die folgende Aktivität veranschaulicht:  
  
-   Anwenden eines Shaders auf ein 3D-Modell  
  
## <a name="applying-a-shader-to-a-3-d-model"></a>Anwenden eines Shaders auf ein 3D-Modell  
 Sie können einen Shadereffekt auf ein 3D-Modell anwenden, um ihm ein interessantes Aussehen zu verleihen.  
  
 Bevor Sie beginnen, stellen Sie sicher, dass das Fenster **Eigenschaften** angezeigt wird.  
  
#### <a name="to-apply-a-shader-to-a-3-d-model"></a>Anwenden eines Shaders auf ein 3D-Modell  
  
1.  Beginnen Sie mit einer 3D-Szene, die ein oder mehrere Modelle enthält. Wenn Sie keine geeignete 3D-Szene haben, erstellen Sie eine wie in [Vorgehensweise: Erstellen eines 3D-Basismodells](../designers/how-to-create-a-basic-3-d-model.md) beschrieben wird. Sie müssen ebenso über einen DGSL-Shader verfügen, den Sie auf das Modell anwenden können. Wenn Sie keinen geeigneten Shader haben, erstellen Sie einen wie es in [Vorgehensweise: Erstellen eines standardmäßigen Farbshaders](../designers/how-to-create-a-basic-color-shader.md), und stellen Sie sicher, dass er in einer Datei gespeichert wurde, bevor Sie fortfahren.  
  
2.  Wählen Sie das Modell, auf das Sie den Shader anwenden möchten, im Modus **Auswählen** aus. Anschließend legen Sie im Fenster **Eigenschaften** unter der Eigenschaft **Dateiname** in der Eigenschaftsgruppe **Effekt** den DGSL-Shader fest, den Sie auf das Modell anwenden möchten.  
  
 Hier finden Sie ein Modell, bei dem der grundlegende Farbeffekt angewendet wurde:  
  
 ![3D-Szene zur Darstellung des grundlegenden Farbeffekts](../designers/media/digit-3d-model-effect.png "Digit-3D-Modelleffekt")  
  
 Nachdem Sie einen Shader auf ein Modell angewendet haben, können Sie es im Shader-Designer durch Auswählen des Modells öffnen und anschließend die Schaltfläche „Ellipse“ (**...**) im Fenster **Eigenschaften** unter der Eigenschaft **(Erweitert)** der Eigenschaftsgruppe **Effekt** auswählen.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines 3D-Basismodells](../designers/how-to-create-a-basic-3-d-model.md)   
 [Vorgehensweise: Erstellen eines standardmäßigen Farbshaders](../designers/how-to-create-a-basic-color-shader.md)   
 [Modell-Editor](../designers/model-editor.md)   
 [Shader-Designer](../designers/shader-designer.md)



