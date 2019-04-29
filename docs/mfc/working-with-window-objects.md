---
title: Arbeiten mit Fensterobjekten
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: c696d880ffa69b0a0399c5282621546c5783ebe4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399485"
---
# <a name="working-with-window-objects"></a>Arbeiten mit Fensterobjekten

Arbeiten mit Windows-Aufrufe für zwei Arten von Aktivitäten:

- Verarbeiten von Windows-Meldungen

- Zeichnen im Fenster

Um Windows-Nachrichten in einem Fenster, einschließlich Ihrer eigenen untergeordneten Fenster zu verarbeiten, finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md) , die Nachrichten zu einer C++-Fenster-Klasse zuzuordnen. Klicken Sie dann schreiben Sie Meldungshandler-Memberfunktionen in der Klasse.

Die meisten Zeichnen in einer Framework-Anwendung erfolgt in der Ansicht, deren [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion aufgerufen wird, wenn der Inhalt des Fensters gezeichnet werden müssen. Wenn das Fenster ein untergeordnetes Element der Ansicht ist, können Sie einige der Funktionen zum Zeichnen der Ansicht in das untergeordnete Fenster delegieren, indem Sie mit `OnDraw` rufen Sie eine der Memberfunktionen des Fensters.

In jedem Fall benötigen Sie einen Gerätekontext zum Zeichnen. Sie können die vordefinierten Stift, Pinsel und andere Grafikobjekte enthalten, die in den Gerätekontext, die Ihr Fenster zugeordnet sind. Oder Sie können diese Objekte rufen Sie die Zeichnungseffekte ignoriert, die Sie benötigen. Der Gerätekontext, richten Sie, wie Sie möchten, rufen die Memberfunktionen der Klasse [CDC](../mfc/reference/cdc-class.md) (Gerätekontextklasse) zum Zeichnen von Linien, Formen und Text, Farben zu verwenden und mit einem Koordinatensystem arbeiten.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

- [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)

- [Gerätekontexte](../mfc/device-contexts.md)

- [Grafikobjekte](../mfc/graphic-objects.md)

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)
