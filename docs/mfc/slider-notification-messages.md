---
title: Benachrichtigungsmeldungen des Schieberegler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c383458905d16dda935254e56a5aa9f56a153e83
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956160"
---
# <a name="slider-notification-messages"></a>Benachrichtigungsmeldungen des Schieberegler-Steuerelements
Ein Schieberegler-Steuerelement benachrichtigt das übergeordnete Fenster von Benutzeraktionen, durch das Senden von Nachrichten von WM_HSCROLL oder WM_VSCROLL, abhängig von der Ausrichtung des Schieberegler-Steuerelements für des übergeordnete Elements. Um diese Nachrichten behandeln zu können, fügen Sie Ereignishandler für die WM_HSCROLL und WM_VSCROLL Nachrichten an das übergeordnete Fenster. Die [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) und [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) Memberfunktionen werden übergeben, eine Benachrichtigungscode, der die Position des Schiebereglers und einen Zeiger auf die [CSliderCtrl](../mfc/reference/csliderctrl-class.md) Objekt. Beachten Sie, dass der Zeiger vom Typ `CScrollBar *` , obwohl er auf verweist ein `CSliderCtrl` Objekt. Sie müssen möglicherweise den this-Zeiger umgewandelt werden, wenn Sie das Schieberegler-Steuerelement bearbeiten müssen.  
  
 Statt der Bildlaufleiste Benachrichtigung senden Schieberegler-Steuerelemente einen anderen Satz von Benachrichtigungscodes. Ein Schieberegler-Steuerelement sendet den Codes der Benachrichtigung Benachrichtigungscodes TB_BOTTOM, TB_LINEDOWN TB_LINEUP und TB_TOP nur, wenn der Benutzer ein Schieberegler-Steuerelement mithilfe der Tastatur interagiert. Die benachrichtigungsmeldungen TB_THUMBPOSITION-Benachrichtigungscode und TB_THUMBTRACK werden nur gesendet, wenn der Benutzer die Maus verwendet wird. In beiden Fällen werden die TB_ENDTRACK, TB_PAGEDOWN und TB_PAGEUP Benachrichtigungscodes gesendet.  
  
 Die folgende Tabelle enthält die benachrichtigungsmeldungen des Schieberegler-Steuerelement und die Ereignisse (virtuelle Tastencodes oder Mausereignisse), die dazu führen, dass die Benachrichtigungen gesendet werden. (Eine Liste der standardmäßigen virtuellen Tastencodes, finden Sie unter Winuser.h.)  
  
|Benachrichtigungsmeldung|Ereignis verursacht hat die Benachrichtigung gesendet werden|  
|--------------------------|-------------------------------------------|  
|BENACHRICHTIGUNGSCODES TB_BOTTOM|VK_END|  
|TB_ENDTRACK|WM_KEYUP (der Benutzer hat einen Schlüssel, der relevanten virtuellen Tastencode gesendet)|  
|TB_LINEDOWN|VK_RIGHT oder VK_DOWN|  
|TB_LINEUP|VK_LEFT oder VK_UP|  
|TB_PAGEDOWN|VK_NEXT (der Benutzer geklickt hat den Kanal unten oder rechts neben dem Schieberegler)|  
|TB_PAGEUP|VK_PRIOR (der Benutzer geklickt hat den Kanal oben oder links neben dem Schieberegler)|  
|TB_THUMBPOSITION-BENACHRICHTIGUNGSCODE|Befolgen eine Benachrichtigung TB_THUMBTRACK WM_LBUTTONUP|  
|TB_THUMBTRACK|Schieberegler-Verschiebung (der Benutzer gezogen, den Schieberegler)|  
|TB_TOP|VK_HOME|  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

