---
title: Von Animationssteuerelementen gesendete Benachrichtigungen
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 8c437e6950435b49c280c4f1bb9225002545d6f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449295"
---
# <a name="notifications-sent-by-animation-controls"></a>Von Animationssteuerelementen gesendete Benachrichtigungen

Ein Animationssteuerelement ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) zwei verschiedene Arten von Benachrichtigungen sendet. Die Benachrichtigungen werden gesendet, in Form von [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachrichten.

Die [ACN_START](/windows/desktop/Controls/acn-start) Nachricht wird gesendet, wenn das Animationssteuerelement gestartet wurde, einen Audioclip abspielen. Die [ACN_STOP](/windows/desktop/Controls/acn-stop) Nachricht wird gesendet, wenn das Animationssteuerelement abgeschlossen oder beendet einen Audioclip abspielen.

## <a name="see-also"></a>Siehe auch

[Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

