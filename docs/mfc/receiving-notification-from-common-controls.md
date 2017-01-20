---
title: "Empfangen von Benachrichtigungen von Standardsteuerelementen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ON_NOTIFY"
  - "WM_NOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allgemeine Steuerelemente [C++], Benachrichtigungen"
  - "Steuerelemente [MFC], Benachrichtigungen"
  - "Benachrichtigungen, Allgemeine Steuerelemente"
  - "ON_NOTIFY-Makro"
  - "OnNotify-Methode"
  - "Empfangen von Benachrichtigungen von Standardsteuerelementen"
  - "Allgemeine Windows-Steuerelemente [C++], Benachrichtigungen"
  - "WM_NOTIFY-Meldung"
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Empfangen von Benachrichtigungen von Standardsteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Allgemeine Steuerelemente sind untergeordnete Fenster, die Benachrichtigungsmeldungen auf das übergeordnete Fenster gesendet werden, wenn Ereignisse, wie Benutzereingaben, im Steuerelement auftreten.  
  
 Die Anwendung ist auf diesen Benachrichtigungsmeldungen, um zu bestimmen, welche Aktionen der Benutzer ausführen möchte.  Die gebräuchlichsten Steuerelementen senden Benachrichtigungsmeldungen als **WM\_NOTIFY** Meldungen.  Windows\-Steuerelemente senden die meisten Benachrichtigungsmeldungen als **WM\_COMMAND** Meldungen.  [CWnd::OnNotify](../Topic/CWnd::OnNotify.md) ist der Handler für die **WM\_NOTIFY** Meldung.  Wie `CWnd::OnCommand`, stellt die Implementierung von `OnNotify` die Benachrichtigung an `OnCmdMsg` für die Behandlung in den Meldungszuordnungen aus.  Der Eintrag in der Meldungszuordnung für das Behandeln der Benachrichtigungen ist `ON_NOTIFY`.  Weitere Informationen finden Sie unter [Technischer Hinweis 61: ON\_NOTIFY\- und WM\_NOTIFY\-Meldungen](../mfc/tn061-on-notify-and-wm-notify-messages.md).  
  
 Alternativ kann eine abgeleitete Klasse eigene Benachrichtigungsmeldungen mit "Meldungsreflektion bearbeiten." Weitere Informationen finden Sie unter [Technischer Hinweis 62: Meldungs\-Reflektion für Windows\-Steuerelemente](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
## Abrufen der Cursorposition in einer Benachrichtigung  
 Bei Möglichkeit ist es hilfreich, die aktuellen Cursorposition zu bestimmen, ob bestimmte Benachrichtigungsmeldungen durch eine freigegebene Steuerelement empfangen werden.  Beispielsweise kann es hilfreich sein, der aktuellen Cursorposition zu bestimmen, wenn eine gemeinsame **NM\_RCLICK**\-Steuerelement\-MFC\-Klassen eine Benachrichtigung empfängt.  
  
 Es gibt eine einfache Möglichkeit, dies zu erreichen, indem `CWnd::GetCurrentMessage` aufgerufen wird.  ruft jedoch diese Methode nur die Cursorplatzierung ab, wenn die Nachricht gesendet wurde.  Da der Cursor möglicherweise verschoben, seit die Nachricht gesendet wurde, müssen Sie **CWnd::GetCursorPos** aufrufen, um die aktuellen Cursorposition abzurufen.  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage` sollte in einem Meldungshandlers nur aufgerufen werden.  
  
 Fügen Sie folgenden Code den Text des Benachrichtigungsmeldungshandlers hinzu \(in diesem Beispiel, **NM\_RCLICK**\):  
  
 [!CODE [NVC_MFCControlLadenDialog#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#4)]  
  
 An diesem Punkt wird der Mauszeigerspeicherort im `cursorPos`\-Objekt gespeichert.  
  
## Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)