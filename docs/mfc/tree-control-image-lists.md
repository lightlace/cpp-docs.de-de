---
title: "Bilderliste für das Struktursteuerelement | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- images [MFC], lists in tree controls
- tree controls [MFC], image lists
- CTreeCtrl class [MFC], image lists
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5015a001bf2c15f3144303ba5e19b2a9ea8c34f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-image-lists"></a>Bilderliste für das Struktursteuerelement
Jedes Element in einem Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kann ein Paar von Bitmapbildern zugeordnet haben. Die Bilder werden auf der linken Seite der Bezeichnung eines Elements angezeigt. Ein Bild wird angezeigt, wenn das Element ausgewählt ist, und der andere wird angezeigt, wenn das Element nicht ausgewählt ist. Beispielsweise kann ein Element angezeigt einen Ordner öffnen, wenn diese Option ausgewählt ist und einen geschlossenen Ordner, wenn es nicht aktiviert ist.  
  
 Um Element Images verwenden zu können, müssen Sie eine Bildliste erstellen, durch das Erstellen einer [CImageList](../mfc/reference/cimagelist-class.md) Objekt und Verwenden der [CImageList:: Create](../mfc/reference/cimagelist-class.md#create) Funktion, um die zugeordnete Bildliste zu erstellen. Klicken Sie dann der Liste die gewünschte Bitmaps hinzu, und ordnen Sie die Liste mithilfe des Strukturansicht-Steuerelements die [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist) Memberfunktion. Standardmäßig werden alle Elemente das erste Bild in der Bildliste für die ausgewählten und nicht ausgewählten Status angezeigt. Sie können das Standardverhalten für ein bestimmtes Element ändern, indem Sie die Indizes der ausgewählten und nicht ausgewählten Bilder angeben, wenn Sie das Element dem Strukturansicht-Steuerelement mit Hinzufügen der [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) Memberfunktion. Sie können die Indizes nach dem Hinzufügen eines Elements mit ändern die [Memberfunktion SetItemImage](../mfc/reference/ctreectrl-class.md#setitemimage) Memberfunktion.  
  
 Bilderliste für das Strukturansicht-Steuerelements können auch Overlaybilder enthalten, die entwickelt wurden, um das Elementbilder überlagert werden. Ein Wert ungleich NULL in Bits 8 bis 11 für eine Strukturansicht-Steuerelement ein Element des Status Gibt den einsbasierten Index ein Overlaybild (0 bedeutet keine Overlay-Image). Da ein 4-Bit, einsbasierten Index verwendet wird, müssen zwischen der ersten 15-Images in der Bildliste Overlaybilder sein. Weitere Informationen über Elementzustände des struktursteuerung-Steuerelements finden Sie unter [Struktur Steuerelement Übersicht über Elementzustände](../mfc/tree-control-item-states-overview.md) weiter oben in diesem Thema.  
  
 Wenn eine Bildliste Status angegeben ist, reserviert eine Strukturansicht Speicherplatz auf der linken Seite des Symbols jedes Element, für die Image-Status. Status-Bilder, z. B. Kontrollkästchen aktiviert und deaktiviert, können eine Anwendung anwendungsdefinierte Elementzustände angegeben. Ein Wert ungleich NULL in Bits 12 bis 15 gibt den einsbasierten Index eines statusbilds (0 bedeutet keine statusbilds).  
  
 Durch Angabe der **I_IMAGECALLBACK** Wert anstelle der Index eines Bilds, können Sie verzögern, ausgewählte oder nicht ausgewählten Bild angeben, bis das Element ist zu neu gezeichnet wird. **I_IMAGECALLBACK** leitet des Strukturansicht-Steuerelements zum Abfragen von der Anwendung für den Index durch Senden der [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) Benachrichtigung.  
  
 Die [Memberfunktion GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist) Memberfunktion Ruft das Handle der Bildliste ein Strukturansicht-Steuerelement ab. Diese Funktion ist nützlich, wenn Sie weitere Images zur Liste hinzufügen müssen. Weitere Informationen zu Bildlisten, finden Sie unter [Verwenden von CImageList](../mfc/using-cimagelist.md), [CImageList](../mfc/reference/cimagelist-class.md) in der *MFC-Referenz*, und [Bilderlisten](http://msdn.microsoft.com/library/windows/desktop/bb761389) in der Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

