---
title: Meldungsbehandlung und -zuordnung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
ms.openlocfilehash: 0321d98d8b92af0b80259bc49e84e69b987577a4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508243"
---
# <a name="message-handling-and-mapping"></a>Meldungsbehandlung und -zuordnung

In dieser Artikel Familie wird beschrieben, wie Nachrichten und Befehle vom MFC-Framework verarbeitet werden und wie Sie diese mit ihren Handlerfunktionen verbinden.

In herkömmlichen Programmen für Windows werden Windows-Meldungen in einer großen Switch-Anweisung in einer Fenster Prozedur behandelt. MFC verwendet stattdessen [Nachrichten](../mfc/message-categories.md) Zuordnungen, um direkte Nachrichten zu unterschiedlichen Klassenmember-Funktionen zuzuordnen. Meldungs Zuordnungen sind für diesen Zweck effizienter als virtuelle Funktionen und ermöglichen das Verarbeiten von Nachrichten durch das geeignetste C++ Objekt – Anwendung, Dokument, Ansicht usw. Sie können eine einzelne Nachricht oder einen Bereich von Nachrichten, Befehls-IDs oder Steuerelement-IDs zuordnen.

WM_COMMAND Messages – wird normalerweise von Menüs, Symbolleisten Schaltflächen oder Accelerators generiert – verwenden Sie auch den Message-Map-Mechanismus. MFC definiert ein Standard [Routing](../mfc/command-routing.md) von Befehls Meldungen zwischen der Anwendung, dem Rahmen Fenster, der Ansicht und den aktiven Dokumenten in Ihrem Programm. Sie können dieses Routing bei Bedarf außer Kraft setzen.

Meldungs Zuordnungen bieten außerdem eine Möglichkeit zum Aktualisieren von Benutzeroberflächen Objekten (z. b. Menüs und Symbolleisten Schaltflächen), deren Aktivierung oder Deaktivierung für den aktuellen Kontext.

Allgemeine Informationen zu Nachrichten und Nachrichten Warteschlangen in Windows finden Sie unter [Meldungen und Nachrichten](/windows/win32/winmsg/messages-and-message-queues) Warteschlangen in der Windows SDK.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

- [Aufrufen eines Nachrichten Handlers durch das Framework](../mfc/how-the-framework-calls-a-handler.md)

- [So durchsucht das Framework Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md)

- [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)

- [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)

- [Anzeigen von Befehls Informationen in der Status Leiste](../mfc/how-to-display-command-information-in-the-status-bar.md)

- [Dynamisches Aktualisieren von Benutzeroberflächen Objekten](../mfc/how-to-update-user-interface-objects.md)

- [Vorgehensweise: Erstellen einer Meldungszuordnung für eine Vorlagenklasse](../mfc/how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)<br/>
[CWnd-Klasse](../mfc/reference/cwnd-class.md)<br/>
[CCmdTarget-Klasse](../mfc/reference/ccmdtarget-class.md)
