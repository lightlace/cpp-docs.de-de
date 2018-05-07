---
title: Hinzufügen von Elementen zum Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eab0c7cb1aebf1675d078aa99941edfd9afdc5a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adding-items-to-the-control"></a>Hinzufügen von Elementen zum Steuerelement
Hinzufügen von Elementen auf das Strukturelement-Steuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)), rufen Sie eine der verschiedenen Versionen von der [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) Memberfunktion ist, je nachdem welche Informationen Sie. Eine Version übernimmt einen [LV_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) -Struktur, die Sie vorbereiten. Da die `LV_ITEM` Struktur enthält zahlreiche Elemente, stehen Ihnen mehr Kontrolle über die Attribute des Listenelements-Steuerelement.  
  
 Zwei wichtige Member (hinsichtlich der Berichtsansicht) von der `LV_ITEM` Struktur werden die `iItem` und `iSubItem` Elemente. Die `iItem` Member ist der nullbasierte Index des Elements verweist auf die Struktur und die `iSubItem` Member ist der einsbasierte Index des Unterelements oder 0 (null), wenn die Struktur Informationen über ein Element enthält. Mit diesen beiden Membern bestimmen Sie, pro Element, dem Typ und Wert der Unterelementinformationen, die angezeigt wird, wenn das Strukturelement-Steuerelement in der Berichtsansicht ist. Weitere Informationen finden Sie unter [CListCtrl:: SetItem](../mfc/reference/clistctrl-class.md#setitem).  
  
 Zusätzliche Member geben Sie des Elements Text, Symbol ", Status und Elementdaten. "Elementdaten" ein anwendungsdefinierten Wert, der eine Listenansichtselements zugeordnet ist. Weitere Informationen zu den `LV_ITEM` -Struktur, finden Sie unter [CListCtrl:: GetItem](../mfc/reference/clistctrl-class.md#getitem).  
  
 Andere Versionen von `InsertItem` nehmen Sie eine oder mehrere unterschiedliche Werte, die für Elemente in der `LV_ITEM` -Struktur, sodass Sie nur die Elemente zu initialisieren, Sie unterstützen möchten. Im Allgemeinen können das Strukturelement-Steuerelement verwaltet den Speicher für Listenelemente, Sie jedoch speichern einige Informationen in Ihrer Anwendung stattdessen mithilfe von "Rückrufelemente". Weitere Informationen finden Sie unter [Rückrufelemente und Rückrufmaske](../mfc/callback-items-and-the-callback-mask.md) in diesem Thema und [Rückrufelemente und Rückrufmaske](http://msdn.microsoft.com/library/windows/desktop/bb774736) im Windows SDK.  
  
 Weitere Informationen finden Sie unter [hinzufügen Listenansicht Elemente und Unterelemente](http://msdn.microsoft.com/library/windows/desktop/bb774736).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

