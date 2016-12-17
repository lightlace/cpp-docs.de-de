---
title: "Overlaymasken in Bildlisten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList-Klasse, Bildüberlagerungen in"
  - "Bilderlisten [C++], Bildüberlagerungen in"
  - "Überlagerungen"
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Overlaymasken in Bildlisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede Bildliste \([CImageList](../mfc/reference/cimagelist-class.md)\) enthält eine Liste von Bildern, die als Overlaymasken zu verwenden.  Eine "Overlaymaske" ist ein Bild, die transparent über ein anderes Bild gezeichnet wird.  Jedes Bild kann als Overlaymaske verwendet werden.  Sie können bis zu vier Overlaymasken pro Bildliste angeben.  
  
 Sie fügen den Index eines Bilds der Liste der Overlaymasken, indem Sie die Memberfunktion [SetOverlayImage](../Topic/CImageList::SetOverlayImage.md), den Index verwenden, eines Bilds und den Index einer Overlaymaske hinzu.  Beachten Sie, dass die Indizes für die Overlaymasken anstatt nullbasiert 1\-basiert sind.  
  
 Zeichnen Sie eine Overlaymaske über ein Bild mit einem einzelnen Aufruf **Zeichnen**.  Die Parameter enthalten den Index des Bilds, um zu zeichnen und den Index einer Overlaymaske.  Sie müssen das [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408)\-Makro verwenden, um den Index der Overlaymaske anzugeben.  Sie können einem Overlaybild auch angeben, wenn Sie die [DrawIndirect](../Topic/CImageList::DrawIndirect.md)\-Memberfunktion aufrufen.  
  
## Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)