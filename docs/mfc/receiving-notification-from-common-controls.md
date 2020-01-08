---
title: Empfangen von Benachrichtigungen von Standardsteuerelementen
ms.date: 11/04/2016
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
ms.openlocfilehash: 73315d4a1107204bc6adc885729fdeeaeb7f98d0
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298973"
---
# <a name="receiving-notification-from-common-controls"></a>Empfangen von Benachrichtigungen von Standardsteuerelementen

Allgemeine Steuerelemente sind untergeordnete Fenster, die Benachrichtigungs Meldungen an das übergeordnete Fenster senden, wenn Ereignisse, z. b. Eingaben vom Benutzer, im Steuerelement auftreten.

Die Anwendung nutzt diese Benachrichtigungs Meldungen, um zu bestimmen, welche Aktion der Benutzer ausführen möchte. Die meisten gängigen Steuerelemente senden Benachrichtigungs Meldungen als WM_NOTIFY-Nachrichten. Windows-Steuerelemente senden die meisten Benachrichtigungs Meldungen als WM_COMMAND Nachrichten. [CWnd:: OnNotify](../mfc/reference/cwnd-class.md#onnotify) ist der Handler für die WM_NOTIFY Nachricht. Wie bei `CWnd::OnCommand`sendet die-Implementierung von `OnNotify` die Benachrichtigungs Meldung an `OnCmdMsg` zur Verarbeitung in Nachrichten Zuordnungen. Der Meldungs Zuordnungs Eintrag für die Behandlung von Benachrichtigungen ist ON_NOTIFY. Weitere Informationen finden Sie unter [Technical Note 61: ON_NOTIFY und WM_NOTIFY Messages](../mfc/tn061-on-notify-and-wm-notify-messages.md).

Alternativ kann eine abgeleitete Klasse ihre eigenen Benachrichtigungs Meldungen mithilfe von "Message Reflection" verarbeiten. Weitere Informationen finden Sie unter [technischer Hinweis 62: Nachrichten Reflektion für Windows](../mfc/tn062-message-reflection-for-windows-controls.md)-Steuerelemente.

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Abrufen der Cursor Position in einer Benachrichtigungs Meldung

Gelegentlich ist es hilfreich, die aktuelle Position des Cursors zu ermitteln, wenn bestimmte Benachrichtigungs Meldungen von einem gemeinsamen Steuerelement empfangen werden. Beispielsweise kann es hilfreich sein, die aktuelle Cursorposition zu bestimmen, wenn ein gemeinsames Steuerelement eine NM_RCLICK Benachrichtigungs Meldung empfängt.

Dies ist eine einfache Möglichkeit, dies durch Aufrufen von `CWnd::GetCurrentMessage`zu erreichen. Diese Methode ruft jedoch nur die Cursorposition zu dem Zeitpunkt ab, an dem die Nachricht gesendet wurde. Da der Cursor nach dem Senden der Nachricht verschoben werden kann, müssen Sie `CWnd::GetCursorPos` zum Abrufen der aktuellen Cursorposition abrufen.

> [!NOTE]
>  `CWnd::GetCurrentMessage` sollte nur innerhalb eines Nachrichten Handlers aufgerufen werden.

Fügen Sie dem Text des Benachrichtigungs Meldungs Handlers (in diesem Beispiel NM_RCLICK) den folgenden Code hinzu:

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

An diesem Punkt wird die Mauszeigerposition im `cursorPos` Objekt gespeichert.

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
