---
title: "Benachrichtigungsmeldungen des Schieberegler-Steuerelements"
ms.custom: na
ms.date: "12/03/2016"
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
  - "CSliderCtrl-Klasse, Benachrichtigungen"
  - "Meldungen, Benachrichtigung"
  - "Benachrichtigungen, CSliderCtrl"
  - "Schieberegler-Steuerelemente, Benachrichtigungsmeldungen"
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Benachrichtigungsmeldungen des Schieberegler-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Slider\-Steuerelement benachrichtigt sein übergeordnetes Fenster Benutzeraktionen, indem übergeordnete `WM_HSCROLL` oder die `WM_VSCROLL` \- Meldungen, je nach Ausrichtung des Schieberegler\-Steuerelements sendet.  Um diese Nachrichten behandeln, fügen Sie Handler für die Meldungen `WM_HSCROLL` und `WM_VSCROLL` dem übergeordneten Fenster hinzu.  Der [OnHScroll](../Topic/CWnd::OnHScroll.md) und [OnVScroll](../Topic/CWnd::OnVScroll.md)\-Memberfunktionen werden einem Benachrichtigungscode, die Position des Schiebereglers und ein Zeiger auf das [CSliderCtrl](../mfc/reference/csliderctrl-class.md)\-Objekt übergeben.  Beachten Sie, dass der Mauszeiger vom Typ **CScrollBar \*** ist, obwohl sie auf `CSliderCtrl` ein Objekt zeigt.  Sie müssen möglicherweise der Typ diesen Zeiger, wenn Sie das Schieberegler\-Steuerelement bearbeiten müssen.  
  
 Anstatt mithilfe der Bildlaufleistenbenachrichtigungscodes, senden Slider\-Steuerelementen einen anderen Satz Benachrichtigungscodes.  Ein Slider\-Steuerelement sendet die **TB\_BOTTOM**, **TB\_LINEDOWN**, **TB\_LINEUP** und **TB\_TOP** Benachrichtigungscodes nur, wenn der Benutzer auf ein Schieberegler\-Steuerelement interagiert, indem die Tastatur verwendet.  Die **TB\_THUMBPOSITION** und **TB\_THUMBTRACK** Benachrichtigungsmeldungen werden nur gesendet, wenn der Benutzer die Maus verwendet.  Die **TB\_ENDTRACK**, **TB\_PAGEDOWN** und **TB\_PAGEUP** Benachrichtigungscodes werden in beiden Fällen übermittelt.  
  
 Die folgende Tabelle zeigt die Schieberegler\-Steuerelement\-Benachrichtigungsmeldungen und Ereignisse \(virtuelle Tastencodes oder Mausereignisse\) diese Ursache der zu sendenden Benachrichtigungen, auf. \(Eine Liste von Standardvirtuellen, finden Sie tastencodes Winuser.h.\)  
  
|Benachrichtigung|Ereignis, das bewirkt Benachrichtigung gesendet zu werden|  
|----------------------|---------------------------------------------------------------|  
|**TB\_BOTTOM**|**VK\_END**|  
|**TB\_ENDTRACK**|`WM_KEYUP` \(der Benutzer hat einen Schlüssel verwendet, die einen relevanten virtueller Tastencode übermittelten\)|  
|**TB\_LINEDOWN**|**VK\_RIGHT** oder **VK\_DOWN**|  
|**TB\_LINEUP**|**VK\_LEFT** oder **VK\_UP**|  
|**TB\_PAGEDOWN**|**VK\_NEXT** \(der Benutzer klicken auf den Channel unter oder auf der rechten Seite den Schieberegler\)|  
|**TB\_PAGEUP**|**VK\_PRIOR** \(der Benutzer klicken auf den Channel über bzw. auf der linken Seite den Schieberegler\)|  
|**TB\_THUMBPOSITION**|`WM_LBUTTONUP` nach einer **TB\_THUMBTRACK** Benachrichtigung|  
|**TB\_THUMBTRACK**|Schiebereglerbewegung \(der Benutzer zog den Schieberegler\)|  
|**TB\_TOP**|**VK\_HOME**|  
  
## Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)