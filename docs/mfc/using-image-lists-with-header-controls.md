---
title: Mit Image in Headersteuerelementen Listet | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2da3737b54c53903f8fc8ff30cccba6165cbde45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-image-lists-with-header-controls"></a>Verwenden von Bildlisten in Headersteuerelementen
Headerelemente haben die Möglichkeit, ein Bild in einem Headerelement anzuzeigen. Dieses Bild in einer zugeordneten Bildliste gespeicherten beträgt 16 x 16 Pixel und verfügt über dieselben Merkmale wie die Symbolbilder in einem Listenansicht-Steuerelement verwendet. Um dieses Verhalten erfolgreich zu implementieren, müssen Sie zuerst erstellen und initialisieren die Bildliste, ordnen Sie die Liste mit dem Headersteuerelement und ändern Sie die Attribute des Headerelements, das das Bild angezeigt wird.  
  
 Das folgende Verfahren veranschaulicht die Details, die mithilfe eines Zeigers auf ein Headersteuerelement (`m_pHdrCtrl`) und einen Zeiger auf eine Bildliste (`m_pHdrImages`).  
  
### <a name="to-display-an-image-in-a-header-item"></a>Um ein Bild in einem Headerelement anzuzeigen.  
  
1.  Erstellen Sie eine neue Bildliste (oder verwenden Sie ein vorhandenes Image Listenobjekt) mithilfe der [CImageList](../mfc/reference/cimagelist-class.md) Speichern des resultierenden Zeigers-Konstruktor.  
  
2.  Initialisieren Sie das neue Image Listenobjekt durch Aufrufen von [CImageList:: Create](../mfc/reference/cimagelist-class.md#create). Der folgende Code ist ein Beispiel für diesen Aufruf.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]  
  
3.  Fügen Sie die Bilder für jeden Headerelement hinzu. Der folgende Code fügt zwei vordefinierte Images.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]  
  
4.  Ordnen Sie die Bildliste des Headersteuerelements mit einem Aufruf von [:: SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist).  
  
5.  Ändern Sie das Headerelement, um ein Bild aus der Liste zugeordnete Bild anzuzeigen. Im folgende Beispiel weist das erste Bild aus `m_phdrImages`, für die erste Headerelement `m_pHdrCtrl`.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]  
  
 Ausführliche Informationen zu den Parameterwerten verwendet, finden Sie in der entsprechenden [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md).  
  
> [!NOTE]
>  Es ist möglich, mehrere Steuerelemente, die über dieselbe Bildliste verfügen. Z. B. in einem standard-Listenansicht-Steuerelement, es kann einer Bildliste (von 16 x 16 Pixel großen Bildern) von sowohl von der kleinen Symbolansicht von einem Listenansicht-Steuerelement und die Headerelemente eines Listenansicht-Steuerelement verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)

