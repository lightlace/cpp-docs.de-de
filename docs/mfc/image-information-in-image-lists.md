---
title: "Bildinformationen in Bildlisten | Microsoft Docs"
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
  - "CImageList-Klasse, Bildinformationen in"
  - "Bilderlisten [C++], Bildinformationen in"
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Bildinformationen in Bildlisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CImageList](../mfc/reference/cimagelist-class.md) enthält mehrere Funktionen, die Informationen aus einer Bildliste abrufen.  Die Memberfunktion [GetImageInfo](../Topic/CImageList::GetImageInfo.md) füllt eine Struktur `IMAGEINFO` mit Informationen über einem Einzelbild, einschließlich verarbeitet die Bild\- und Maskenbitmaps, der Anzahl von Farbenebenen und \-Bits pro Pixel und des umgebenden Rechtecks des Bilds in der Bildbitmaps aus.  Sie können diese Informationen verwenden, um die Bitmap des Bildes direkt zu bearbeiten.  
  
 Die [GetImageCount](../Topic/CImageList::GetImageCount.md)\-Memberfunktion wird die Anzahl von Bildern in einer Bildliste ab.  
  
 Sie können ein Symbol auf einem Bild und Maske in einer Bildliste erstellen, indem Sie die Memberfunktion [ExtractIcon](../Topic/CImageList::ExtractIcon.md) verwenden.  Die Funktion gibt das Handle des neuen Symbols zurück.  
  
## Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)