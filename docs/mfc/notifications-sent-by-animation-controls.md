---
title: Von Animationssteuerelementen gesendete Benachrichtigungen
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 2a736e4315091b1b26daceb4fe0ce9672ab33ff6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238308"
---
# <a name="notifications-sent-by-animation-controls"></a>Von Animationssteuerelementen gesendete Benachrichtigungen

Ein Animationssteuerelement ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) zwei verschiedene Arten von Benachrichtigungen sendet. Die Benachrichtigungen werden gesendet, in Form von [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachrichten.

Die [ACN_START](/windows/desktop/Controls/acn-start) Nachricht wird gesendet, wenn das Animationssteuerelement gestartet wurde, einen Audioclip abspielen. Die [ACN_STOP](/windows/desktop/Controls/acn-stop) Nachricht wird gesendet, wenn das Animationssteuerelement abgeschlossen oder beendet einen Audioclip abspielen.

## <a name="see-also"></a>Siehe auch

[Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
