---
title: Meldungen
ms.date: 11/04/2016
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
ms.openlocfilehash: 8e1bfd1baa8ffef76ba31912fc619c4217696683
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300075"
---
# <a name="messages"></a>Meldungen

Die Nachrichtenschleife in die `Run` Memberfunktion der Klasse `CWinApp` ruft in der Warteschlange Nachrichten, die durch verschiedene Ereignisse generiert. Klickt der Benutzer die Maus, sendet Windows beispielsweise mehrere mausbezogenen-Meldungen, z. B. WM_LBUTTONDOWN, wenn die linke Maustaste gedrückt wird und WM_LBUTTONUP, wenn die linke Maustaste losgelassen wird. Die Framework Implementierung der Meldungsschleife Anwendung sendet die Nachricht an das entsprechende Fenster.

Die wichtigsten Kategorien von Nachrichten werden in beschrieben [Meldungskategorien](../mfc/message-categories.md).

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)
