---
title: Von Animationssteuerelementen gesendete Benachrichtigungen
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 68ede3bc55669a29eef192d38b29b8c1ab433e4b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508017"
---
# <a name="notifications-sent-by-animation-controls"></a>Von Animationssteuerelementen gesendete Benachrichtigungen

Ein Animations Steuerelement ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) sendet zwei verschiedene Typen von Benachrichtigungs Meldungen. Die Benachrichtigungen werden in Form von [WM_COMMAND](/windows/win32/menurc/wm-command) -Nachrichten gesendet.

Die [ACN_START](/windows/win32/Controls/acn-start) -Nachricht wird gesendet, wenn das Animations Steuerelement mit der Wiedergabe eines Clips begonnen hat. Die [ACN_STOP](/windows/win32/Controls/acn-stop) -Nachricht wird gesendet, wenn das Animations Steuerelement beendet wurde oder die Wiedergabe eines Clips beendet hat.

## <a name="see-also"></a>Siehe auch

[Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
