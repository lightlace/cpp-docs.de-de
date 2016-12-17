---
title: "Drag &amp; Drop-Operationen f&#252;r das Struktursteuerelement"
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
  - "CTreeCtrl-Klasse, Drag & Drop-Operationen"
  - "Drag & Drop, CTreeCtrl"
  - "Struktursteuerelemente, Drag & Drop-Operationen"
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Drag &amp; Drop-Operationen f&#252;r das Struktursteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) sendet eine Benachrichtigung wenn der Benutzer beginnt, per ein Element ziehen.  Das Steuerelement sendet eine Benachrichtigung [TVN\_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504), wenn der Benutzer beginnt, ein Element mit der linken Maustaste und eine Benachrichtigung [TVN\_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) ziehen, wenn der Benutzer das Ziehen mit der rechten Schaltfläche gestartet wird.  Sie können eine Strukturansicht am Senden dieser Benachrichtigungen verhindern, indem Sie dem **TVS\_DISABLEDRAGDROP**\-Strukturansicht das Format geben.  
  
 Sie erhalten ein Bild, die während eines Ziehvorgangs anzuzeigen, indem Sie die Memberfunktion [CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md) aufrufen.  Das Tree\-Steuerelement erstellt eine ziehende Bitmap auf der Bezeichnung des Elements, das gezogen wird.  Dann erstellt das Struktursteuerelement Bildlisten, fügt der Bitmap hinzu und gibt einen Zeiger auf das [CImageList](../mfc/reference/cimagelist-class.md)\-Objekt zurück.  
  
 Sie müssen den Code bereitstellen, der tatsächlich das Element gezogen werden.  Dies umfasst normalerweise ziehenden, die Funktionen der Bildlistenfunktionen mit ein und die gesendeten [WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) und [WM\_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) \(oder [WM\_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)\) Nachrichten verarbeiten, nachdem der Ziehvorgang gestartet wurde.  Weitere Informationen über die Bildlistenfunktionen, finden Sie unter [CImageList](../mfc/reference/cimagelist-class.md) in der *MFC\-Referenz* und [Grafiklisten](http://msdn.microsoft.com/library/windows/desktop/bb761389) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Weitere Informationen zum das Ziehen eines Strukturansicht\-Steuerelement\-Elements, finden Sie unter [Ziehen des Strukturansichtelements](http://msdn.microsoft.com/library/windows/desktop/bb760017), in [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 Wenn sich Elemente in einer Strukturansicht, die Ziele eines Drag & Drop\-Vorgangs sein sollen, müssen Sie wissen, dass der Mauszeiger auf einem Zielelement ist.  Sie können ermitteln, indem Sie die Memberfunktion [HitTest](../Topic/CTreeCtrl::HitTest.md) aufrufen.  Sie entweder einem Punkt und ganzzahligen oder der Adresse [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) einer Struktur an, die die aktuellen Koordinaten des Mauszeigers enthält.  Wenn die Funktion beendet wird, enthält die gesamte Zahl oder Struktur ein Flag, die Position des Mauszeigers relativ zum Strukturansicht angibt.  Wenn der Cursor über ein Element in der Strukturansicht ist, enthält die Struktur das Handle des Elements auch.  
  
 Sie können angeben, dass ein Element das Ziel eines Drag & Drop\-Vorgangs ist, indem die [SetItem](../Topic/CTreeCtrl::SetItem.md)\-Memberfunktion aufruft, um den Zustand auf den Wert `TVIS_DROPHILITED` festzulegen.  Ein Element, das den Zustand hat, wird im Format gezeichnet, das verwendet wird, um einem Drag & Drop\-Ziel anzugeben.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)