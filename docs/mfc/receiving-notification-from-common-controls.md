---
title: Empfangen von Benachrichtigungen von Standardsteuerelementen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs: C++
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
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58131874ed039378a312acaaa238388f335f8e71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="receiving-notification-from-common-controls"></a>Empfangen von Benachrichtigungen von Standardsteuerelementen
Allgemeine Steuerelemente sind untergeordnete Fenster, die benachrichtigungsmeldungen an das übergeordnete Fenster zu senden, wenn Ereignisse, wie Eingaben des Benutzers im Steuerelement auftreten.  
  
 Die Anwendung verwendet diese benachrichtigungsmeldungen, um zu bestimmen, welche Aktion der Benutzer es durchführen möchte. Am häufigsten verwendeten Steuerelemente Senden von benachrichtigungsmeldungen als **WM_NOTIFY** Nachrichten. Windows-Steuerelemente senden, als die meisten benachrichtigungsmeldungen **WM_COMMAND** Nachrichten. [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) ist der Handler für das **WM_NOTIFY** Nachricht. Wie bei `CWnd::OnCommand`, die Implementierung von `OnNotify` verteilt die Benachrichtigung `OnCmdMsg` für die Behandlung in meldungszuordnungen. Der meldungszuordnung Eintrag für die Verarbeitung von Benachrichtigungen ist `ON_NOTIFY`. Weitere Informationen finden Sie unter [technischen Hinweis 61: ON_NOTIFY- und WM_NOTIFY-Meldungen](../mfc/tn061-on-notify-and-wm-notify-messages.md).  
  
 Alternativ können Sie behandeln eine abgeleitete Klasse einen eigenen benachrichtigungsmeldungen mithilfe von "Meldungsreflektion." Weitere Informationen finden Sie unter [technischen Hinweis 62: Meldung Reflektion für Windows-Steuerelemente](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Abrufen der Cursorposition in einer Benachrichtigung  
 In manchen Fällen ist es hilfreich, die die aktuelle Position des Cursors ermitteln, wenn bestimmte benachrichtigungsmeldungen von eines allgemeinen Steuerelements empfangen werden. Beispielsweise wäre es hilfreich, die zur aktuellen Cursorposition zu bestimmen, wann ein allgemeinen Steuerelements empfängt eine **NM_RCLICK** benachrichtigungsmeldung.  
  
 Es ist eine einfache Möglichkeit hierzu durch Aufrufen von `CWnd::GetCurrentMessage`. Allerdings ruft diese Methode nur die Cursorposition ab, zu dem Zeitpunkt, der die Nachricht gesendet wurde. Da der Cursor verschoben wurde, da die Nachricht gesendet wurde, rufen Sie **GetCursorPos** zum Abrufen der aktuellen Cursorposition.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage`sollte nur in Message-Handler aufgerufen werden.  
  
 Fügen Sie den folgenden Code in den Text der Benachrichtigung Message-Handler (in diesem Beispiel **NM_RCLICK**):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 An diesem Punkt wird die Position des Mauszeigers Cursors gespeichert, der `cursorPos` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

