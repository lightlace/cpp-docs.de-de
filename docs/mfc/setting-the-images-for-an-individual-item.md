---
title: "Festlegen der Bilder für ein einzelnes Element | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d9cb74c2290292f44b8c6c9b8797890e759f315
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setting-the-images-for-an-individual-item"></a>Festlegen der Bilder für ein bestimmtes Element
Die verschiedenen Typen von Bildern, durch die erweiterten Kombinationsfeldelement werden bestimmt anhand der Werte in der `iImage`, **iSelectedImage**, und **iOverlay** Mitglied der [COMBOBOXEXITEM ](http://msdn.microsoft.com/library/windows/desktop/bb775746) Struktur. Jeder Wert ist der Index eines Bilds in der zugehörigen Bildliste des Steuerelements. Standardmäßig werden diese Member auf 0 festgelegt, verursacht das Steuerelement kein Bild für das Element an. Wenn Sie Bilder für ein bestimmtes Element verwenden möchten, können Sie die Struktur entsprechend beim Einfügen der Kombinationsfeldelement oder durch Ändern einer vorhandenen Kombinationsfeldelement ändern.  
  
## <a name="setting-the-image-for-a-new-item"></a>Einstellen des Bildes für ein neues Element  
 Wenn Sie ein neues Element einfügen, initialisieren Sie die `iImage`, **iSelectedImage**, und **iOverlay** Strukturmember mit den richtigen Werten, und fügen Sie dann das Element mit einem Aufruf von [ CComboBoxEx:: InsertItem](../mfc/reference/ccomboboxex-class.md#insertitem).  
  
 Das folgende Beispiel fügt ein neue erweiterte Kombinationsfeldelement (`cbi`) in der erweiterten Kombinationsfeld-Steuerelement (`m_comboEx`), stellt Indizes für alle drei Zustände Abbild:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_1.cpp)]  
  
## <a name="setting-the-image-for-an-existing-item"></a>Einstellen des Bildes für ein vorhandenes Element  
 Wenn Sie ein vorhandenes Element ändern, müssen Sie zur Bearbeitung der **Maske** Mitglied einer **COMBOBOXEXITEM** Struktur.  
  
#### <a name="to-modify-an-existing-item-to-use-images"></a>So ändern Sie ein vorhandenes Element zum Verwenden von Bildern  
  
1.  Deklarieren Sie eine **COMBOBOXEXITEM** -Struktur, und legen Sie die **Maske** -Datenmember auf die Werte sind Sie interessiert, ändern.  
  
2.  Diese Struktur mit einen Aufruf von stellen [:: GetItem](../mfc/reference/ccomboboxex-class.md#getitem).  
  
3.  Ändern der **Maske**, `iImage`, und **iSelectedImage** Member neu zurückgegebenen Struktur, die entsprechenden Werte verwendet.  
  
4.  Rufen Sie [CComboBoxEx::SetItem](../mfc/reference/ccomboboxex-class.md#setitem), und übergeben Sie die geänderte Struktur.  
  
 Im folgende Beispiel veranschaulicht dieses Verfahren durch Austausch der ausgewählten und nicht ausgewählten Images für das dritte Element der erweiterten Kombinationsfeld-Feld:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/cpp/setting-the-images-for-an-individual-item_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

