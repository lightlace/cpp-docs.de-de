---
title: "Meldungskategorien | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "command-Meldungen [C++]"
  - "Steuerelemente-Benachrichtigungsmeldungen"
  - "Steuerelemente [MFC], Benachrichtigungen"
  - "Meldungsbehandlung [C++], Meldungstypen"
  - "Nachrichten [C++], Kategorien"
  - "Nachrichten [C++], Windows"
  - "Windows-Nachrichten [C++], Kategorien"
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Meldungskategorien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für welche Arten von Meldungen schreiben Sie Handler?  Es gibt drei Hauptkategorien:  
  
1.  Windows\-Meldungen  
  
     Dies umfasst hauptsächlich die Meldungen ein, die dem Präfix **WM\_**, nur **WM\_COMMAND** starten.  Windows\-Meldungen werden über Fenster und Ansichten.  Diese Meldungen verfügen oft Parameter, die verwendet werden, wenn Sie bestimmt, wie die Meldung verarbeitet.  
  
2.  Steuerelementbenachrichtigungen  
  
     Dies schließt **WM\_COMMAND** Benachrichtigungsmeldungen von Steuerelementen und anderen untergeordneten Fenstern an ihre übergeordnete Fenster ein.  Beispielsweise überträgt ein Bearbeitungssteuerelement der übergeordnete **WM\_COMMAND** eine Meldung, die dem **EN\_CHANGE**\-Steuerelementbenachrichtigungscode enthält, wenn der Benutzer Aktionen durchgeführt wurde, die möglicherweise im Bearbeitungssteuerelement Text geändert.  Der Handler des Fensters für die Meldung reagiert auf die Benachrichtigung auf eine entsprechende Weise, z Abrufen des Texts im Steuerelement.  
  
     Das Framework leitet Steuerelement\-Benachrichtigungen wie andere **WM\_** weiter Meldungen.  Eine Ausnahme besteht jedoch die **BN\_CLICKED**\-Steuerelement\-Benachrichtigung, die durch Schaltflächen gesendet wird, wenn der Benutzer auf sie klickt.  Diese Meldung ist speziell als Befehlsmeldung behandelt und weitergeleitet wie andere Befehle.  
  
3.  Befehlsmeldungen  
  
     Dies schließt **WM\_COMMAND** Benachrichtigungsmeldungen von Benutzeroberflächenobjekten ein: Menüs, Symbolleisten\-Schaltflächen und Zugriffstasten.  Das Framework verarbeitet Befehle als mit anderen Meldungen, und sie können von mehrere Arten von Objekten behandelt werden, wie in [Befehls\-Ziele](../mfc/command-targets.md) erläutert wurde.  
  
##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Windows\-Meldungen und Steuerelement\-Benachrichtigungen  
 Nachrichten in Kategorien 1 und 2 \- Windows\-Meldungen und Steuerelementbenachrichtigungen \- werden durch Fenster behandelt: Objekte von den Klassen abgeleitet von der Klasse `CWnd`.  Hierzu gehören `CFrameWnd`, `CMDIFrameWnd`, `CMDIChildWnd`, `CView`, `CDialog` und eigene Klassen, die aus diesen Basisklassen abgeleitet werden.  Solche Objekte `HWND` kapseln, ein Handle zu einem Windows\-Fenster.  
  
##  <a name="_core_command_messages"></a> Befehlsmeldungen  
 Nachrichten in Kategorie 3 \- Befehle \- können durch eine größere Bandbreite von Objekten bearbeitet werden: Dokumente, Dokumentvorlagen und das Anwendungsobjekt selbst sowie den Fenstern und \- Ansichten.  Wenn ein Befehl direkt ein bestimmtes Objekt auswirkt, ist es sinnvoll, dieses Objekt verfügen der Befehl.  Beispielsweise wird der offene Befehl im Menü Datei logisch mit der Anwendung zugeordnet: die Anwendung öffnet ein bestimmtes Dokument nach Empfang des Befehls.  Daher ist der Handler für den geöffneten Befehl eine Memberfunktion der Anwendungsklasse.  Weitere Informationen über Befehle und wie sie auf Objekte weitergeleitet werden, finden Sie unter [Wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md).  
  
## Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)