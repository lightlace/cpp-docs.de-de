---
title: "Bildlistenarten | Microsoft Docs"
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
  - "CImageList-Klasse, Typen"
  - "Bilderlisten [C++], Typen"
  - "Listen [C++], Bild"
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Bildlistenarten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei Typen Grafiklisten \([CImageList](../mfc/reference/cimagelist-class.md)\): nicht maskiert und maskiert.  Eine "nicht maskierten Bildliste" besteht aus einer Farbenbitmap, die eine oder mehrere Bilder enthält.  Eine "maskierte Bildliste" besteht zwei Bitmaps aus gleicher Größe.  Das erste Element ist eine Farbenbitmap, der die Bilder enthält, und das zweite ist eine monochrome Bitmap, die eine Reihe Masken \- eine für jedes Bild in der ersten Bitmap enthält.  
  
 Eine der Überladungen der **Erstellen**\-Memberfunktion wird ein Flag, um anzugeben, ob die Bildliste maskiert wird. \(Die übrigen Überladungen erstellen maskierte Bildlisten.\)  
  
 Wenn ein nicht maskiertes Bild gezeichnet wird, ist es einfach in den Zielgerätekontext kopiert; das heißt, wird es über der vorhandenen Hintergrundfarbe des Gerätekontexts gezeichnet.  Wenn ein maskiertes Bild gezeichnet wird, werden die Bits des Bildes mit den Teilen der Maske kombiniert und normalerweise erzeugen transparente Bereiche in der Bitmap, die Hintergrundfarbe des Zielgerätekontexts durch darstellt.  Sie können einigen Zeichnungsformaten angeben, wenn Sie ein maskiertes Bild gefüllt.  Beispielsweise können Sie angeben, dass das Bild gerastert wird, um ausgewählte Objekt anzugeben.  
  
## Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)