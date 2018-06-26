---
title: Empfangen von Benachrichtigungen von Standardsteuerelementen | Microsoft Docs
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
ms.openlocfilehash: 80fefde054ed411dcb30836b2b89cef89cc54e64
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928793"
---
# <a name="receiving-notification-from-common-controls"></a>Empfangen von Benachrichtigungen von Standardsteuerelementen
Allgemeine Steuerelemente sind untergeordnete Fenster, die benachrichtigungsmeldungen an das übergeordnete Fenster zu senden, wenn Ereignisse, wie Eingaben des Benutzers im Steuerelement auftreten.  
  
 Die Anwendung verwendet diese benachrichtigungsmeldungen, um zu bestimmen, welche Aktion der Benutzer es durchführen möchte. Am häufigsten verwendeten Steuerelemente werden benachrichtigungsmeldungen als WM_NOTIFY-Meldungen senden. Windows-Steuerelemente werden die meisten benachrichtigungsmeldungen als WM_COMMAND-Meldungen senden. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) ist der Handler für die WM_NOTIFY-Meldung. Wie bei `CWnd::OnCommand`, die Implementierung von `OnNotify` verteilt die Benachrichtigung `OnCmdMsg` für die Behandlung in meldungszuordnungen. Die Meldungszuordnungseintrags für die Verarbeitung von Benachrichtigungen ist ON_NOTIFY. Weitere Informationen finden Sie unter [technischen Hinweis 61: ON_NOTIFY- und WM_NOTIFY-Meldungen](../mfc/tn061-on-notify-and-wm-notify-messages.md).  
  
 Alternativ können Sie behandeln eine abgeleitete Klasse einen eigenen benachrichtigungsmeldungen mithilfe von "Meldungsreflektion." Weitere Informationen finden Sie unter [technischen Hinweis 62: Meldung Reflektion für Windows-Steuerelemente](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Abrufen der Cursorposition in einer Benachrichtigung  
 In manchen Fällen ist es hilfreich, die die aktuelle Position des Cursors ermitteln, wenn bestimmte benachrichtigungsmeldungen von eines allgemeinen Steuerelements empfangen werden. Beispielsweise wäre es hilfreich, die zur aktuellen Cursorposition zu bestimmen, wann ein allgemeines Steuerelement eine NM_RCLICK-Benachrichtigung erhält.  
  
 Es ist eine einfache Möglichkeit hierzu durch Aufrufen von `CWnd::GetCurrentMessage`. Allerdings ruft diese Methode nur die Cursorposition ab, zu dem Zeitpunkt, der die Nachricht gesendet wurde. Da der Cursor verschoben wurde, da die Nachricht gesendet wurde, rufen Sie `CWnd::GetCursorPos` zum Abrufen der aktuellen Cursorposition.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage` sollte nur in Message-Handler aufgerufen werden.  
  
 Fügen Sie den folgenden Code in den Text der Benachrichtigung-Message-Handler (in diesem Beispiel NM_RCLICK):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 An diesem Punkt wird die Position des Mauszeigers Cursors gespeichert, der `cursorPos` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

