---
title: Mitteilungen
ms.date: 11/04/2016
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
ms.openlocfilehash: 033edfd289ea075b89e9d44111da94b987177470
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434540"
---
# <a name="messages"></a>Mitteilungen

Die Nachrichtenschleife in die `Run` Memberfunktion der Klasse `CWinApp` ruft in der Warteschlange Nachrichten, die durch verschiedene Ereignisse generiert. Klickt der Benutzer die Maus, sendet Windows beispielsweise mehrere mausbezogenen-Meldungen, z. B. WM_LBUTTONDOWN, wenn die linke Maustaste gedrückt wird und WM_LBUTTONUP, wenn die linke Maustaste losgelassen wird. Die Framework Implementierung der Meldungsschleife Anwendung sendet die Nachricht an das entsprechende Fenster.

Die wichtigsten Kategorien von Nachrichten werden in beschrieben [Meldungskategorien](../mfc/message-categories.md).

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

