---
title: Verwenden von Bildlisten in einem erweiterten Kombinationsfeld-Steuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ac69e7d0dbe1748a409b107579c747b7f9a4a7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>Verwenden von Bildlisten in einem erweiterten Kombinationsfeld-Steuerelement
Die Hauptfunktion des erweiterten Kombinationsfeld-Steuerelementen ist die Möglichkeit, einzelne Elemente in einem Kombinationsfeld-Steuerelement von Bildern aus einer Bildliste zugeordnet werden soll. Jedes Element wird auf drei verschiedene Bilder anzeigen: eine für den ausgewählten Zustand, für die nicht ausgewählten Zustand und ein drittes Bild überlagert.  
  
 Das folgende Verfahren ordnet eine Bildliste mit einem erweiterten Kombinationsfeld-Steuerelement:  
  
### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>Zuordnen eine Bildliste mit einem erweiterten Kombinationsfeld-Steuerelement  
  
1.  Erstellen Sie eine neue Bildliste (oder verwenden Sie ein vorhandenes Listenobjekt in Image), mit der [CImageList](../mfc/reference/cimagelist-class.md) Konstruktor und das Speichern des resultierenden Zeigers.  
  
2.  Initialisieren Sie das neue Image Listenobjekt durch Aufrufen von [CImageList:: Create](../mfc/reference/cimagelist-class.md#create). Der folgende Code ist ein Beispiel für diesen Aufruf.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  Fügen Sie optionale Bilder für die verschiedenen statusmöglichkeiten: ausgewählten oder nicht ausgewählt und ein Overlay. Der folgende Code fügt drei vordefinierte Images.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  Ordnen Sie die Bildliste mit dem Steuerelement mit einem Aufruf von [CComboBoxEx:: SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist).  
  
 Nachdem die Bildliste dem Steuerelement zugeordnet wurde, können Sie die Bilder, die jedes Element der drei mögliche Zustände verwendet werden sollen, einzeln angeben. Weitere Informationen finden Sie unter [Festlegen der Bilder für ein einzelnes Element](../mfc/setting-the-images-for-an-individual-item.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

