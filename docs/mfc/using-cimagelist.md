---
title: "Verwenden von CImageList | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImageList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList-Klasse, Verwenden"
  - "Bilderliste-Steuerelement"
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Verwenden von CImageList
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit einer Bildliste, dargestellt durch Klasse [CImageList](../mfc/reference/cimagelist-class.md), ist eine Auflistung gleich\-skalierte Bilder, von denen jedes über seinen Index verwiesen werden kann.  Grafiklisten werden verwendet, um große Sätze Symbole oder Bitmaps effizient verwalten.  Grafiklisten sind nicht auch Steuerelemente, da sie beim Fenster sind; Sie sollten diese mit verschiedenen Typen Steuerelemente, u Listensteuerelemente \([Verwendung](../mfc/reference/clistctrl-class.md)\), der \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) und Tab\-Steuerelemente \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) verwendet.  
  
 Alle Bilder in einer Bildliste werden in einer einzelnen, Anordnen Bitmap im Bildschirmgeräteformat enthalten.  Mit einer Bildliste enthält möglicherweise auch eine monochrome Bitmap, die die Masken enthält, die verwendet werden, um Bilder transparent zu zeichnen \(Symbolformat\).  `CImageList` stellt Memberfunktionen, die Sie aktivieren, um Bilder zu zeichnen, Bildlisten erstellen oder zerstören muss, Bilder hinzufügen und entfernen, ersetzen Bilder, Zusammenführungsbilder und Bilder.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Grafiklisten von Typen](../mfc/types-of-image-lists.md)  
  
-   [Mit einer Bildliste](../mfc/using-an-image-list.md)  
  
-   [Bearbeiten von Bildlisten](../mfc/manipulating-image-lists.md)  
  
-   [Zeichnungs\-Bilder einer Bildliste](../mfc/drawing-images-from-an-image-list.md)  
  
-   [Bild\-Overlays in den Bildlisten](../mfc/image-overlays-in-image-lists.md)  
  
-   [Ziehen von Bildern von einer Bildliste](../mfc/dragging-images-from-an-image-list.md)  
  
-   [Bild\-Informationen in den Bildlisten](../mfc/image-information-in-image-lists.md)  
  
## Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)