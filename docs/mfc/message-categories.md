---
title: Meldungskategorien
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
ms.openlocfilehash: 07d9e706e8ed01a81ee580e7c4e11fa1f1a7a8df
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326243"
---
# <a name="message-categories"></a>Meldungskategorien

Welche Arten von Nachrichten Sie Handler schreiben, für die es gibt drei Hauptkategorien unterteilt:

1. Windows-Meldungen

   Dazu gehören in erster Linie die Nachrichten, die seit der **WM_** außer WM_COMMAND-Präfix. Windows-Nachrichten werden von Windows und Ansichten behandelt. Diese Meldungen verfügen häufig über Parameter, die bestimmen, wie zur Verarbeitung der Nachricht verwendet werden.

1. Steuerelementbenachrichtigungen

   Dies schließt WM_COMMAND-benachrichtigungsmeldungen aus den Steuerelementen und anderen untergeordneten Fenster an ihre übergeordnete Fenster. Z. B. sendet ein Bearbeitungssteuerelement dem übergeordnete Element eine WM_COMMAND-Meldung, die den Code der EN_CHANGE-Ereignis-Steuerelement-Benachrichtigung, wenn der Benutzer eine Aktion ausgeführt hat, die Text im Bearbeitungssteuerelement geändert haben kann. -Handler des Fensters für die Nachricht antwortet auf die Benachrichtigung in einer geeigneten Weise, wie z. B. das Abrufen des Texts im Steuerelement.

   Das Framework leitet wie andere Steuerelemente-benachrichtigungsmeldungen **WM_** Nachrichten. Einzige Ausnahme ist jedoch die BN_CLICKED steuerelementebenachrichtigung Nachricht, die durch Schaltflächen gesendet werden, wenn der Benutzer darauf klickt. Diese Meldung dient speziell als Befehlsnachricht behandelt und wie andere Befehle geleitet.

1. Command-Meldungen

   Dies schließt WM_COMMAND-Benachrichtigungen von Benutzeroberflächenobjekten: Menüs, Symbolleisten-Schaltflächen und Zugriffstasten. Das Framework verarbeitet die Befehle anders als andere Nachrichten und können durch weitere Arten von Objekten behandelt werden, wie unter [Befehlsziele](../mfc/command-targets.md).

##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Windows-Nachrichten und Steuerelemente-Benachrichtigungsmeldungen

Nachrichten in die Kategorien 1 und 2 – Windows-Nachrichten und steuerelementbenachrichtigungen – von Windows behandelt werden: Objekte der Klassen, die von der Klasse abgeleitet `CWnd`. Dies schließt `CFrameWnd`, `CMDIFrameWnd`, `CMDIChildWnd`, `CView`, `CDialog`, und Ihre eigenen Klassen, die von diesen Basisklassen abgeleitet. Solche Objekte schließen einen `HWND`, ein Handle für ein Windows-Fenster.

##  <a name="_core_command_messages"></a> Command-Meldungen

Nachrichten in der Kategorie 3 – Befehle – verarbeitet werden können, indem Sie eine größere Anzahl von Objekten: Dokumente, Dokumentvorlagen und der Application-Objekt selbst, zusätzlich zu Windows und Ansichten. Wenn Sie ein Befehl direkt auf ein bestimmtes Objekt auswirkt, ist es sinnvoll, die das Objekt, das den Befehl behandeln zu müssen. Z. B. der Befehl "Öffnen" im Menü Datei der Anwendung logisch zugeordnet ist: die Anwendung öffnet ein angegebenes Dokument den Befehl empfängt. Daher wird der Handler für den Befehl zum Öffnen eine Memberfunktion der Klasse. Weitere Informationen zu Befehlen und wie sie auf Objekte weitergeleitet werden, finden Sie unter [wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)
