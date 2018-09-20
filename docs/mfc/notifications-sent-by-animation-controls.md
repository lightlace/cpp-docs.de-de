---
title: Von Animationssteuerelementen gesendete Benachrichtigungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb83fe6195c01c1e9dbcc2c00e43738af9ebc8e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386391"
---
# <a name="notifications-sent-by-animation-controls"></a>Von Animationssteuerelementen gesendete Benachrichtigungen

Ein Animationssteuerelement ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) zwei verschiedene Arten von Benachrichtigungen sendet. Die Benachrichtigungen werden gesendet, in Form von [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachrichten.

Die [ACN_START](/windows/desktop/Controls/acn-start) Nachricht wird gesendet, wenn das Animationssteuerelement gestartet wurde, einen Audioclip abspielen. Die [ACN_STOP](/windows/desktop/Controls/acn-stop) Nachricht wird gesendet, wenn das Animationssteuerelement abgeschlossen oder beendet einen Audioclip abspielen.

## <a name="see-also"></a>Siehe auch

[Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

