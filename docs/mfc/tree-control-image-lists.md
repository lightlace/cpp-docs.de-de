---
title: "Bilderliste f&#252;r das Struktursteuerelement"
ms.custom: na
ms.date: "12/14/2016"
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
  - "CTreeCtrl-Klasse, Bilderlisten"
  - "Bilder [C++], Listen in Struktursteuerelementen"
  - "Struktursteuerelemente, Bilderlisten"
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Bilderliste f&#252;r das Struktursteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jedes Element in einem der Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) kann ein Paar Bitmapbilder haben, die zugeordnet.  Die Bilder werden links neben der Bezeichnung eines Elements.  Ein Bild wird angezeigt, wenn das Element ausgewählt ist, und das andere wird angezeigt, wenn das Element nicht ausgewählt ist.  Beispielsweise könnte ein Element einen geöffneten Ordner angezeigt, wenn ein geschlossener und Ordner ausgewählt wird, wenn nicht ausgewählt wird.  
  
 Um Elementbilder zu verwenden, müssen Sie einer Bildliste erstellen mithilfe eines [CImageList](../mfc/reference/cimagelist-class.md)\-Objekt erstellen und die [CImageList::Create](../Topic/CImageList::Create.md)\-Funktion verwenden um die zugeordnete Bildliste zu erstellen.  Fügen Sie dann den gewünschten Bitmaps der Liste hinzu, und ordnen Sie die Liste mit dem Strukturansicht\-Steuerelement zu, indem Sie die Memberfunktion [SetImageList](../Topic/CTreeCtrl::SetImageList.md) verwenden.  Standardmäßig werden alle Elemente des ersten Bild in der Bildliste für die ausgewählten und nicht ausgewählten Zustände an.  Sie können das Standardverhalten für ein bestimmtes Element ändern, indem Sie Indizes der ausgewählten und nicht ausgewählten Bilder angeben, wenn Sie das Element dem Strukturansicht\-Steuerelement mithilfe der Memberfunktion [InsertItem](../Topic/CTreeCtrl::InsertItem.md) hinzufügen.  Sie können entweder die Indizes ändern, nachdem Sie einem Element hinzugefügt haben, indem Sie die Memberfunktion [SetItemImage](../Topic/CTreeCtrl::SetItemImage.md) verwenden.  
  
 Die Bildlisten einer Strukturansicht können Overlaybilder auch enthalten, die entwickelt wurden, auf Elementbildern angeordnet werden.  Ein Wert ungleich 0 in Bits 8 bis 11 aus dem Zustand eines Strukturansicht\-Steuerelement\-Elements 1\-basierte gibt den Index eines Overlaybilds an \(0 gibt keinen Overlaybild an\).  Da ein 4\-Bit, einsbasierter Index verwendet wird, müssen Overlaybilder zu den ersten 15 Bildern in von Bildlisten gehören.  Weitere Informationen über Strukturansicht\-Steuerelement\-Elementzustände, finden Sie unter [Übersicht Strukturansicht\-Steuerelement\-Element gibt an](../mfc/tree-control-item-states-overview.md) weiter oben in diesem Thema.  
  
 Wenn eine Zustandsbildliste angegeben, ein Strukturansicht\-Steuerelement\-Reservenleerzeichen auf der linken Seite des Symbols jedes Elements für ein Zustandsbild.  Eine Anwendung kann z Zustandsbilder, überprüften und gelöschte Kontrollkästchen verwenden, um Elementzuständen anwendungsdefinierten anzugeben.  Ein Wert ungleich 0 in Bits 12 bis 15 ist dem mit Eins beginnenden Index eines Zustandsbilds an \(0 gibt keinen Zustandsbild an\).  
  
 Mit dem **I\_IMAGECALLBACK**\-Wert anstelle des Index eines Bilds festlegen, können Sie den, ausgewählten oder nicht ausgewählten Bilds anzugeben verzögern, bis das Element im Begriff ist neu gezeichnet sein.  **I\_IMAGECALLBACK** verweist das Struktursteuerelement, die Anwendung für den Index durchführen, indem Sie die [TVN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) Benachrichtigung gesendet.  
  
 Die Memberfunktion [GetImageList](../Topic/CTreeCtrl::GetImageList.md) ruft das Handle die Bildliste einer Strukturansicht ab.  Diese Funktion ist nützlich, wenn Sie weitere Bilder der Liste hinzufügen müssen.  Weitere Informationen über Bildlisten, finden Sie unter [Verwenden CImageList](../mfc/using-cimagelist.md), [CImageList](../mfc/reference/cimagelist-class.md) in der *MFC\-Referenz* und [Grafiklisten](http://msdn.microsoft.com/library/windows/desktop/bb761389) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)