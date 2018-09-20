---
title: Benachrichtigungsmeldungen des Schieberegler | Microsoft-Dokumentation
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
ms.openlocfilehash: 775ca98ff19266343631ff54bac16bebfff9e264
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399534"
---
# <a name="slider-notification-messages"></a>Benachrichtigungsmeldungen des Schieberegler-Steuerelements

Ein Schieberegler-Steuerelement benachrichtigt das übergeordnete Fenster von Benutzeraktionen, durch Senden der übergeordneten WM_HSCROLL oder WM_VSCROLL-Meldungen, je nach Ausrichtung des Schieberegler-Steuerelements. Um diese Nachrichten zu verarbeiten, Hinzufügen von Ereignishandlern für die WM_HSCROLL- und WM_VSCROLL-Meldungen für das übergeordnete Fenster. Die [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) und [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) Memberfunktionen werden übergeben werden, eine Benachrichtigungscode, der die Position des Schiebereglers und einen Zeiger auf die [CSliderCtrl](../mfc/reference/csliderctrl-class.md) Objekt. Beachten Sie, dass der Zeiger vom Typ `CScrollBar *` , obwohl er auf zeigt eine `CSliderCtrl` Objekt. Sie müssen möglicherweise this-Zeiger umgewandelt werden soll, wenn Sie das Schieberegler-Steuerelement bearbeiten müssen.

Statt der Bildlaufleiste Notification-Codes zu verwenden, senden Sie Schieberegler-Steuerelemente einen anderen Satz von Benachrichtigungscodes. Ein Schieberegler-Steuerelement sendet die TB_BOTTOM, TB_LINEDOWN, TB_LINEUP und TB_TOP Benachrichtigungscodes nur, wenn der Benutzer über die Tastatur ein Schieberegler-Steuerelement interagiert. Die benachrichtigungsmeldungen TB_THUMBPOSITION und TB_THUMBTRACK werden nur gesendet, wenn der Benutzer die Maus verwendet wird. Die TB_ENDTRACK, TB_PAGEDOWN und TB_PAGEUP Notification-Codes werden in beiden Fällen gesendet.

Die folgende Tabelle enthält die benachrichtigungsmeldungen des Schieberegler-Steuerelement und die Ereignisse (virtuelle Tastencodes oder Mausereignisse), die dazu führen, dass die Benachrichtigungen gesendet werden. (Eine Liste der standardmäßige virtuelle Tastencodes, finden Sie in der Winuser.h.)

|Benachrichtigungsmeldung|Ereignis verursacht hat die Benachrichtigung gesendet werden|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP (der Benutzer hat einen Schlüssel, der einen entsprechenden virtuellen Tastencode gesendet)|
|TB_LINEDOWN|VK_RIGHT oder VK_DOWN|
|TB_LINEUP|VK_LEFT oder VK_UP|
|TB_PAGEDOWN|VK_NEXT (der Benutzer geklickt hat den Kanal unten oder rechts neben dem Schieberegler)|
|TB_PAGEUP|VK_PRIOR (der Benutzer geklickt hat den Kanal nach oben oder auf der linken Seite des Schiebereglers)|
|TB_THUMBPOSITION|Befolgen eine benachrichtigungsmeldung TB_THUMBTRACK WM_LBUTTONUP|
|TB_THUMBTRACK|Schieberegler-Verschiebung (der Benutzer ziehen den Schieberegler)|
|TB_TOP|VK_HOME|

## <a name="see-also"></a>Siehe auch

[Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

