---
title: Listenelemente und Bildlisten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6bd7a97330a8a646a880bf229562dbec9a70181
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="list-items-and-image-lists"></a>Listenelemente und Bildlisten
Ein "Element" in einem Listensteuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) besteht aus einem Symbol, eine Bezeichnung und möglicherweise andere Informationen (in "Unterelementen").  
  
 Die Symbole für Steuerelement Listenelemente werden in Bildlisten enthalten. Eine Bildliste enthält Symbole in voller Größe in der Symbolansicht verwendet wird. Eine zweite, optionale Bildliste enthält kleinere Versionen der gleichen Symbole für die Verwendung in anderen Ansichten des Steuerelements. Eine dritte, optionale Liste enthält die "State"-Bilder, z. B. Kontrollkästchen für die Anzeige vor den kleinen Symbolen in bestimmten Sichten. Eine vierte, optionale Liste enthält Images, die in den einzelnen Header-Elemente des Steuerelements angezeigt werden.  
  
> [!NOTE]
>  Wenn ein Listenansicht-Steuerelement erstellt wird, mit der `LVS_SHAREIMAGELISTS` Stil, Sie sind der Bildliste zerstören, wenn sie nicht mehr verwendet werden. Geben Sie dieses Format, wenn Sie das gleiche Bild zuweisen für mehrere Listensteuerelemente Ansicht Lists; Andernfalls kann mehr als ein Steuerelement versuchen, dieselbe Bildliste zu zerstören.  
  
 Weitere Informationen zu Elementen finden Sie unter [Liste Ansicht Bilderlisten](http://msdn.microsoft.com/library/windows/desktop/bb774736) und [Elemente und Unterelemente](http://msdn.microsoft.com/library/windows/desktop/bb774736) im Windows SDK. Siehe auch Klasse [CImageList](../mfc/reference/cimagelist-class.md) in der *MFC-Referenz* und [Verwenden von CImageList](../mfc/using-cimagelist.md) in dieser Familie von Artikeln.  
  
 Um ein Listenfeld-Steuerelement zu erstellen, müssen Sie angeben Bildlisten verwendet werden, wenn Sie neue Elemente in der Liste einfügen. Das folgende Beispiel veranschaulicht dieses Verfahren, in denen `m_pImagelist` ist ein Zeiger des Typs `CImageList` und `m_listctrl` ist eine `CListCtrl` -Datenmember.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]  
  
 Wenn keine Symbole in der Listenansicht oder Strukturelement-Steuerelement angezeigt werden sollen, erforderlich nicht jedoch Bildlisten.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

