---
title: Verwenden von Bildlisten in einem Symbolleisten-Steuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 507f684a0c5c7a923cd5c8e16bc9578b8b68e511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Verwenden von Bildlisten in einem Symbolleisten-Steuerelement
Standardmäßig werden die von den Schaltflächen in einem Symbolleisten-Steuerelement verwendet Bilder als eine einzelne Bitmap gespeichert. Allerdings können Sie Bilder in einem Satz von Bildlisten speichern. Das Steuerelementobjekt Symbolleiste kann bis zu drei separate Bildlisten verwenden:  
  
-   Aktiviert die Bildliste enthält Bilder für Symbolleisten-Schaltflächen, die derzeit aktiviert sind.  
  
-   Deaktiviert die Bildliste enthält Bilder für Symbolleisten-Schaltflächen, die derzeit deaktiviert sind.  
  
-   Hervorgehoben Bildliste enthält Bilder für Symbolleisten-Schaltflächen, die aktuell hervorgehoben sind. Diese Bildliste wird verwendet, nur, wenn die Symbolleiste verwendet die **TBSTYLE_FLAT** Stil.  
  
 Diese Bildlisten werden von dem Symbolleisten-Steuerelement verwendet, wenn Sie diese mit Zuordnen der `CToolBarCtrl` Objekt. Diese Zuordnung erfolgt durch Aufrufe von [CToolBarCtrl:: SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), und [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).  
  
 MFC verwendet standardmäßig die `CToolBar` Klasse, um Symbolleisten der MFC-Anwendung zu implementieren. Allerdings die `GetToolBarCtrl` Memberfunktion kann verwendet werden, zum Abrufen der eingebettete `CToolBarCtrl` Objekt. Sie können dann Aufrufe an `CToolBarCtrl` Memberfunktionen, die das zurückgegebene Objekt verwenden.  
  
 Im folgende Beispiel wird diese Technik veranschaulicht, indem Sie einen aktivierten zuweisen (`m_ToolBarImages`) "und" deaktiviert (`m_ToolBarDisabledImages`) Bildliste zu einem `CToolBarCtrl` Objekt (`m_ToolBarCtrl`).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  Der vom Symbolleistenobjekt verwendeten Bildliste muss dauerhafte Objekte. Aus diesem Grund sind sie häufig Datenmember einer MFC-Klasse. In diesem Beispiel wird die Hauptframe-Fensterklasse.  
  
 Sobald der Bildliste zugeordnet sind die `CToolBarCtrl` -Objekt, das Framework automatisch das richtige Schaltflächenbild angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

