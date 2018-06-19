---
title: Strukturansicht-Steuerelement Drag & Drop-Vorgänge | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a620c2481b29b80f6d30dd6457716a652f51fd85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382765"
---
# <a name="tree-control-drag-and-drop-operations"></a>Drag & Drop-Operationen für das Struktursteuerelement
Ein Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sendet eine Benachrichtigung, wenn der Benutzer beginnt, ein Element zu ziehen. Sendet das Steuerelement eine [TVN_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504) Benachrichtigung, wenn der Benutzer beginnt, ein Element mit der linken Maustaste ziehen und ein [TVN_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) Benachrichtigung, wenn der Benutzer beginnt mit ziehen mit der rechten Maustaste. Sie können verhindern, dass ein Strukturansicht-Steuerelement diese Benachrichtigungen senden, durch die Vergabe der Strukturansicht die **TVS_DISABLEDRAGDROP** Stil.  
  
 Sie erhalten ein Bild anzuzeigenden während eines Ziehvorgangs durch Aufrufen der [Memberfunktion CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) Memberfunktion. Strukturansicht-Steuerelements erstellt eine ziehen Bitmap basierend auf der Bezeichnung des Elements gezogen wird. Strukturansicht-Steuerelements eine Bildliste erstellt, die Bitmap hinzugefügt, und gibt einen Zeiger auf die [CImageList](../mfc/reference/cimagelist-class.md) Objekt.  
  
 Sie müssen den Code angeben, der tatsächlich das Element zieht. Dies umfasst in der Regel mithilfe der ziehen Funktionen des Image-Liste-Funktionen und Verarbeiten der [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) und [WM_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) (oder [WM_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)) die Nachrichten gesendet, nachdem der Ziehvorgang begonnen wurde. Weitere Informationen zu den Funktionen der Image-Liste finden Sie unter [CImageList](../mfc/reference/cimagelist-class.md) in der *MFC-Referenz* und [Bilderlisten](http://msdn.microsoft.com/library/windows/desktop/bb761389) im Windows SDK. Weitere Informationen zu einem Strukturelement-Steuerelement ziehen, finden Sie unter [ziehen die Ansicht Strukturelement](http://msdn.microsoft.com/library/windows/desktop/bb760017)auch in der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Wenn Elemente in einem Strukturansicht-Steuerelement an das Ziel eines Drag-and-Drop-Vorgangs sind, müssen Sie wissen, wenn der Mauszeiger auf ein Zielelement befindet. Sie können feststellen, durch Aufrufen der [HitTest](../mfc/reference/ctreectrl-class.md#hittest) Memberfunktion. Sie geben einen Punkt und ganze Zahl oder die Adresse des eine [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) Struktur, die die aktuellen Koordinaten des Mauszeigers enthält. Wenn die Funktion zurückgibt, enthält die ganze Zahl oder eine Struktur ein Flag, der angibt, der Position des Mauszeigers relativ zum Steuerelement Strukturansicht. Wenn der Cursor über ein Element in der Strukturansicht-Steuerelement befindet, enthält die Struktur das Handle des Elements als auch an.  
  
 Sie können angeben, dass ein Element das Ziel eines Drag-and-Drop-Vorgangs durch Aufrufen der [SetItem](../mfc/reference/ctreectrl-class.md#setitem) Memberfunktion zum Festlegen des Status, um die `TVIS_DROPHILITED` Wert. Ein Element mit diesem Status wird in den Stil an, dass ein Drag & Drop-Ziel gezeichnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

