---
title: Von MFC verwendete Stile | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.styles
dev_langs:
- C++
helpviewer_keywords:
- edit styles [MFC]
- window styles, in MFC
- styles
- frame windows, styles
- message-box styles
- styles, MFC
- buttons, MFC toolbars
- list boxes, styles
- static styles
- scroll-bar styles [MFC]
- combo boxes, styles
- extended window styles
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 344d2ce3de15403e17f29dc9504253cbb0ade607
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="styles-used-by-mfc"></a>Von MFC verwendete Stile
Verwenden Sie die folgenden Formate, wenn Sie das entsprechende MFC-Objekt erstellen. In den meisten Fällen sind diese Stile festzulegen, der `dwStyle` Parameter der Klasse **erstellen** Funktion.  
  
### <a name="mfc-styles"></a>MFC-Stile  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|[Button-Stile](../../mfc/reference/button-styles.md)|Gilt für [CButton Klasse](../../mfc/reference/cbutton-class.md) Objekte, z. B. Optionsfelder, Kontrollkästchen und Schaltflächen. Geben Sie eine Kombination der Formate in der `dwStyle` Parameter der [CButton::Create](../../mfc/reference/cbutton-class.md#create).|  
|[Kombinationsfeldstile](../../mfc/reference/combo-box-styles.md)|Gilt für [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md) Objekte. Geben Sie eine Kombination der Formate in der `dwStyle` Parameter der [CComboBox::Create](../../mfc/reference/ccombobox-class.md#create).|  
|[Bearbeiten von Stilen](../../mfc/reference/edit-styles.md)|Gilt für [CEdit Class](../../mfc/reference/cedit-class.md) Objekte. Geben Sie eine Kombination der Formate in der `dwStyle` Parameter der [CEdit::Create](../../mfc/reference/cedit-class.md#create).|  
|[Rahmenfensterstile](../../mfc/reference/frame-window-styles-mfc.md)|Gilt für [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md) Objekte. Geben Sie eine Kombination der Formate in der `dwStyle` Parameter der [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create).|  
|[Listenfeldstile](../../mfc/reference/list-box-styles.md)|Gilt für [CListBox-Klasse](../../mfc/reference/clistbox-class.md) Objekte. Geben Sie eine Kombination der Formate in der `dwStyle` Parameter der [CListBox::Create](../../mfc/reference/clistbox-class.md#create).|  
|[Meldungsfeldstile](../../mfc/reference/message-box-styles.md)|Gilt für [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) Elemente. Geben Sie eine Kombination der Formate in der `nType` Parameter der `AfxMessageBox`.|  
|[Stile des Schiebeleisten Steuerelements](../../mfc/reference/scroll-bar-styles.md)|Gilt für [CScrollBar Klasse](../../mfc/reference/cscrollbar-class.md) Objekte. Geben Sie eine Kombination der Formate in der `dwStyle` Parameter der [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create).|  
|[Statische Stile](../../mfc/reference/static-styles.md)|Gilt für [CStatic Klasse](../../mfc/reference/cstatic-class.md) Objekte. Geben Sie eine Kombination der Formate in der `dwStyle` Parameter der [CStatic::Create](../../mfc/reference/cstatic-class.md#create).|  
|[Fensterstile](../../mfc/reference/window-styles.md)|Gilt für [CWnd-Klasse](../../mfc/reference/cwnd-class.md) Objekte. Geben Sie eine Kombination der Formate in der `dwStyle` Parameter der [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) oder [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex).|  
|[Erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md)|Gilt für [CWnd-Klasse](../../mfc/reference/cwnd-class.md) Objekte. Geben Sie eine Kombination der Formate in der `dwExStyle` Parameter der [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex).|  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../mfc/class-library-overview.md)


