---
title: "Von MFC verwendete Stile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.styles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schaltflächen, MFC-Symbolleisten"
  - "Kombinationsfelder, Stile"
  - "Bearbeiten von Stilen [MFC]"
  - "Erweiterte Fensterstile"
  - "Rahmenfenster, Stile"
  - "Listenfelder, Stile"
  - "Meldungsfeldstile"
  - "Bildlaufleisten-Stile (MFC)"
  - "Statische Stile"
  - "Stile"
  - "Stile, MFC"
  - "Fensterstile, in MFC"
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Von MFC verwendete Stile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie die folgende Formate, wenn das entsprechende MFC\-Objekt erstellen.  In den meisten Fällen sind diese Steuerelemente in den `dwStyle`\-Parameter der Klassen **Erstellen** \-Funktion festgelegt.  
  
### MFC\-Formate  
  
|Stil|**Beschreibung**|  
|----------|----------------------|  
|[Formatvorlagen für Schaltflächen](../../mfc/reference/button-styles.md)|Wendet zu [CButton\-Klasse](../../mfc/reference/cbutton-class.md)\-Objekte, z Optionsfelder, Kontrollkästchen und PushButtons.  Geben Sie eine Kombination von Stilen Parameter im `dwStyle` aus [CButton::Create](../Topic/CButton::Create.md) gezeigt.|  
|[Kombinationsfeldformate](../../mfc/reference/combo-box-styles.md)|Wendet zu [CComboBox\-Klasse](../../mfc/reference/ccombobox-class.md)\-Objekte.  Geben Sie eine Kombination von Stilen Parameter im `dwStyle` aus [CComboBox::Create](../Topic/CComboBox::Create.md) gezeigt.|  
|[Bearbeiten Sie Stile](../../mfc/reference/edit-styles.md)|Wendet zu [CEdit\-Klasse](../../mfc/reference/cedit-class.md)\-Objekte.  Geben Sie eine Kombination von Stilen Parameter im `dwStyle` aus [CEdit::Create](../Topic/CEdit::Create.md) gezeigt.|  
|[Rahmenfensterformate](../../mfc/reference/frame-window-styles-mfc.md)|Wendet zu [CFrameWnd\-Klasse](../../mfc/reference/cframewnd-class.md)\-Objekte.  Geben Sie eine Kombination von Stilen Parameter im `dwStyle` aus [CFrameWnd::Create](../Topic/CFrameWnd::Create.md) gezeigt.|  
|[Listenfeldformate](../../mfc/reference/list-box-styles.md)|Wendet zu [CListBox\-Klasse](../../mfc/reference/clistbox-class.md)\-Objekte.  Geben Sie eine Kombination von Stilen Parameter im `dwStyle` aus [CListBox::Create](../Topic/CListBox::Create.md) gezeigt.|  
|[Meldungsfeldformate](../../mfc/reference/message-box-styles.md)|Wendet zu [AfxMessageBox](../Topic/AfxMessageBox.md)\-Elemente.  Geben Sie eine Kombination der Stile im Parameter `nType` einer `AfxMessageBox`.|  
|[Bildlaufleistenformate](../../mfc/reference/scroll-bar-styles.md)|Wendet zu [CScrollBar\-Klasse](../../mfc/reference/cscrollbar-class.md)\-Objekte.  Geben Sie eine Kombination von Stilen Parameter im `dwStyle` aus [CScrollBar::Create](../Topic/CScrollBar::Create.md) gezeigt.|  
|[Statische Stile](../../mfc/reference/static-styles.md)|Wendet zu [CStatic\-Klasse](../../mfc/reference/cstatic-class.md)\-Objekte.  Geben Sie eine Kombination von Stilen Parameter im `dwStyle` aus [CStatic::Create](../Topic/CStatic::Create.md) gezeigt.|  
|[Fensterstile](../../mfc/reference/window-styles.md)|Wendet zu [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)\-Objekte.  Geben Sie eine Kombination von Stilen Parameter im `dwStyle` von [CWnd::Create](../Topic/CWnd::Create.md) oder [CWnd::CreateEx](../Topic/CWnd::CreateEx.md).|  
|[Erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md)|Wendet zu [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)\-Objekte.  Geben Sie eine Kombination von Stilen Parameter im `dwExStyle` aus [CWnd::CreateEx](../Topic/CWnd::CreateEx.md) gezeigt.|  
  
## Siehe auch  
 [Klassenübersicht](../../mfc/class-library-overview.md)