---
title: "Herausziehen von Bildern aus einer Bildliste"
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
  - "CImageList-Klasse, Herausziehen von Bildern aus"
  - "Herausziehen von Bildern aus einer Bildliste"
  - "Bilderlisten [C++], Herausziehen von Bildern aus"
  - "Bilder [C++], Herausziehen aus Bildlisten"
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Herausziehen von Bildern aus einer Bildliste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CImageList](../mfc/reference/cimagelist-class.md) enthält Funktionen zum Ziehen eines Bilds auf dem Bildschirm ein.  Die ziehenden Funktionen verschieben ein Bild in reibungslos, Farbe und ohne Multilingual des Cursors blinkt.  Können maskierte und entlarvte Bilder gezogen werden.  
  
 Die [BeginDrag](../Topic/CImageList::BeginDrag.md)\-Memberfunktion startet einen Ziehvorgang.  Die Parameter enthalten den Index des Bilds, um zu ziehen und den Speicherort des Hotspots innerhalb des Bilds.  Der Hotspot ist ein einzelnes Pixel, das die Funktionen als genaue ziehenden die Bildschirmposition des Bilds erkennen.  Normalerweise legt eine Anwendung den Hotspot, sodass diese mit dem Hotspot des Mauszeigers entspricht.  Die [DragMove](../Topic/CImageList::DragMove.md)\-Memberfunktion bewegt das Bild auf eine neue Position.  
  
 Die [DragEnter](../Topic/CImageList::DragEnter.md)\-Memberfunktion wird die Anfangsposition des Ziehbilds in einem Fenster fest und zeichnet das Bild an der Position.  Die Parameter beinhalten einen Zeiger auf das Fenster, in dem das Bild und einen Punkt zeichnen, der Koordinaten der Anfangsposition innerhalb des Fensters angibt.  Die Koordinaten sind relativ zur linken oberen Ecke des Fensters, nicht der Clientbereich.  Das gilt für alle Bild\-Ziehen funktioniert erfüllt, dass Verwendet als Parameter koordiniert.  Dies bedeutet, dass Sie die Breite von Fensterelementen, beispielsweise Rahmen, der Titelleiste und der Menüleiste es müssen, wenn Sie die Koordinaten der Stelle angeben.  Wenn Sie einem Fensterhandle **NULL** angeben, wenn Sie auf, rufen `DragEnter`, zeichnen die ziehenden Funktionen das Bild im Gerätekontext, der dem im Desktopfenster zugeordnet ist, und die Koordinaten sind relativ zur linken oberen Ecke des Bildschirms.  
  
 `DragEnter` sperrt alle anderen Aktualisierungen am angegebenen Fenster während des Ziehvorgangs.  Wenn Sie eine beliebige Zeichnung während eines Ziehvorgangs, wie Hervorheben des Ziels eines Drag & Drop\-Vorgangs ausführen müssen, können Sie das gezogene Bild vorübergehend ausblenden, indem Sie die Memberfunktion [DragLeave](../Topic/CImageList::DragLeave.md) verwenden.  Sie können die [DragShowNoLock](../Topic/CImageList::DragShowNolock.md)\-Memberfunktion auch verwenden.  
  
 Rufen Sie [EndDrag](../Topic/CImageList::EndDrag.md) auf, wenn Sie das Bild " erfolgen.  
  
 Die Memberfunktion [SetDragCursorImage](../Topic/CImageList::SetDragCursorImage.md) erstellt ein neues Ziehbild, indem die angegebene Abbildung \(in der Regel ein Mauszeigerbild\) mit dem aktuellen Ziehbild kombiniert.  Da die neue ziehenden Funktionen das Bild während eines Ziehvorgangs verwenden, sollten Sie der Windows\-Funktion [ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) verwenden, um den tatsächlichen Mauszeiger auszublenden, nachdem Sie `SetDragCursorImage` aufgerufen haben.  Andernfalls wird möglicherweise das System, zwei Mauszeiger für die Dauer des Ziehvorgangs zu haben.  
  
 Wenn eine Anwendung `BeginDrag` aufruft, erstellt das System eine temporäre, interne Bildliste und Default.css das angegebene Ziehbild zur internen Liste.  Sie können einen Zeiger auf die temporären Ziehbildliste abrufen, indem Sie die Memberfunktion [GetDragImage](../Topic/CImageList::GetDragImage.md) verwenden.  Die Funktion ruft außerdem die aktuelle Ziehposition und den Offset des Ziehbilds relativ zur Ziehposition ab.  
  
## Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)