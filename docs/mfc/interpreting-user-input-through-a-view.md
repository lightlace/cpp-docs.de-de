---
title: Interpretieren der Benutzereingaben in einer Ansicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 974324e296478f0ec36024d4427496d21255fbf7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421396"
---
# <a name="interpreting-user-input-through-a-view"></a>Interpretieren der Benutzereingaben in einer Ansicht

Andere Memberfunktionen der Ansicht behandeln und alle Benutzereingaben zu interpretieren. Definieren Sie Meldungshandler-Memberfunktionen in der Regel in Ihrer Ansichtsklasse verarbeiten:

- Windows [Nachrichten](../mfc/messages.md) von Maus-und Tastaturaktionen generiert.

- [Befehle](../mfc/user-interface-objects-and-command-ids.md) aus Menüs, Symbolleisten-Schaltflächen und Zugriffstasten.

Diese Meldungshandler-Memberfunktionen untersuchen Sie die folgenden Aktionen als Dateneingabe, Auswahl oder bearbeiten, einschließlich des Verschiebens von Daten in und aus der Zwischenablage:

- Mausbewegungen Klicks zieht und Doppelklicks

- Tastatureingaben

- Menübefehle

Welche Windows-Nachrichten die Ansicht Handles hängt die Anforderungen Ihrer Anwendung ab.

[Behandlung und Themen Zuordnen von Meldungen](../mfc/message-handling-and-mapping.md) wird erläutert, wie Befehle Menüelemente und andere Objekte der Benutzeroberfläche zugewiesen und wie die Befehle mit Handlerfunktionen gebunden. [Behandlung und Themen Zuordnen von Meldungen](../mfc/message-handling-and-mapping.md) Außerdem wird erläutert, wie MFC Befehle weitergeleitet und sendet standard Windows-Nachrichten an die Objekte, Handler für diese enthalten.

Beispielsweise kann Ihre Anwendung müssen direkte Maus zeichnen in der Ansicht zu implementieren. Das Scribble-Beispiel veranschaulicht die WM_LBUTTONDOWN, WM_LBUTTONUP und WM_MOUSEMOVE Nachrichten bzw. zu beginnen, fortsetzen und beenden die Zeichnung eines Liniensegments behandelt. Auf der anderen Seite müssen Sie möglicherweise manchmal einen Mausklick in der Ansicht als eine Auswahl zu interpretieren. Der Ansicht des `OnLButtonDown` Handlerfunktion würde, ob der Benutzer auswählen oder wurde zeichnen bestimmen. Wenn Sie ausgewählt haben, würde der Handler für bestimmen, ob der Klick innerhalb der Grenzen eines Objekts in der Ansicht wurde und wenn dies der Fall ist, ändern die Anzeige auf das Objekt als ausgewählt angezeigt wird.

Die Ansicht möglicherweise auch bestimmte Befehle im Menü, z. B. aus dem Menü "Bearbeiten" zum Ausschneiden, kopieren, einfügen oder löschen die ausgewählte Daten, die über die Zwischenablage behandeln. Solcher Handler würden einige des Members Zwischenablage-bezogenen Funktionen der Klasse aufrufen `CWnd` in oder aus der Zwischenablage in ein ausgewählte Datenelement zu übertragen.

## <a name="see-also"></a>Siehe auch

[Verwenden von Ansichten](../mfc/using-views.md)

