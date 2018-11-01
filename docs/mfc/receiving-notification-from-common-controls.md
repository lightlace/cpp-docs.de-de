---
title: Empfangen von Benachrichtigungen von Standardsteuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25979ec1157a4d2beedf96875e6c8c270b3aaaa9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442382"
---
# <a name="receiving-notification-from-common-controls"></a>Empfangen von Benachrichtigungen von Standardsteuerelementen

Allgemeine Steuerelemente sind untergeordnete Fenster, die Benachrichtigungen für das übergeordnete Fenster, beim Auftreten von Ereignissen, wie die Eingabe des Benutzers, im Steuerelement sendet.

Die Anwendung verwendet diese Benachrichtigungen, um zu bestimmen, welche Aktion der Benutzer es durchführen möchte. Am häufigsten verwendeten Steuerelemente werden Nachrichten als WM_NOTIFY-Meldungen senden. Windows-Steuerelemente werden die meisten benachrichtigungsmeldungen als WM_COMMAND-Meldungen senden. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) ist der Handler für die WM_NOTIFY-Meldung. Wie bei `CWnd::OnCommand`, die Implementierung der `OnNotify` sendet die Benachrichtigung `OnCmdMsg` für die Behandlung in meldungszuordnungen. Die Meldungszuordnungseintrags für die Behandlung von Benachrichtigungen ist ON_NOTIFY. Weitere Informationen finden Sie unter [technischen Hinweis 61: ON_NOTIFY- und WM_NOTIFY-Meldungen](../mfc/tn061-on-notify-and-wm-notify-messages.md).

Alternativ können Sie behandeln eine abgeleitete Klasse einen eigenen benachrichtigungsmeldungen, die mit "Meldungsreflektion." Weitere Informationen finden Sie unter [technischen Hinweis 62: Nachricht Reflektion für Windows-Steuerelemente](../mfc/tn062-message-reflection-for-windows-controls.md).

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Abrufen der Cursorposition in einer Benachrichtigung

Gelegentlich ist es hilfreich, um die aktuelle Position des Cursors zu bestimmen, wenn bestimmte Benachrichtigungen von einem allgemeinen Steuerelement empfangen werden. Beispielsweise wäre es hilfreich sein, die die aktuellen Cursorposition zu bestimmen, wenn ein allgemeines Steuerelement eine NM_RCLICK-Benachrichtigung empfängt.

Es ist eine einfache Möglichkeit hierzu durch Aufrufen von `CWnd::GetCurrentMessage`. Allerdings ruft diese Methode nur die Cursorposition ab, zu dem Zeitpunkt, der die Nachricht gesendet wurde. Da sich der Cursor verschoben wurde, da die Nachricht gesendet wurde, rufen Sie `CWnd::GetCursorPos` zum Abrufen der aktuellen Cursorposition.

> [!NOTE]
>  `CWnd::GetCurrentMessage` sollte nur ein Meldungshandler aufgerufen werden.

Fügen Sie in den Hauptteil der Notification Message-Handler (in diesem Beispiel NM_RCLICK) den folgenden Code hinzu:

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

An diesem Punkt befindet sich die Position des Mauszeigers Cursor in die `cursorPos` Objekt.

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

