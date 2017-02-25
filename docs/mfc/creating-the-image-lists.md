---
title: "Erstellen der Bildliste | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListCtrl-Klasse, Erstellen von Bildlisten für"
  - "Bilderlisten [C++], Erstellen für CListCtrl"
  - "Listen [C++], Bild"
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Erstellen der Bildliste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Grafiklisten zu erstellen ist derselbe, dass Sie [CListView](../mfc/reference/clistview-class.md) oder [Verwendung](../mfc/reference/clistctrl-class.md) verwenden.  
  
> [!NOTE]
>  Sie benötigen nur Bildlisten, wenn Ihr Listensteuerelement `LVS_ICON` das Format enthält.  
  
 Verwenden Sie die `CImageList`\-Klasse, um eine oder mehrere Bildlisten zu erstellen \(für maximierte Symbole, kleine Symbole und Zustände\).  Siehe [CImageList](../mfc/reference/cimagelist-class.md) und [Listenansichts\-Bildlisten](http://msdn.microsoft.com/library/windows/desktop/bb774736) finden Sie in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Aufruf für [CListCtrl::SetImageList](../Topic/CListCtrl::SetImageList.md) jede Bildliste; übergeben einen Zeiger an entsprechende `CImageList`\-Objekt.  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)