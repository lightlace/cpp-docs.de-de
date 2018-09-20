---
title: Nachrichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f25c9cc70cec598f975bbd242af83597311bdc7c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392254"
---
# <a name="messages"></a>Mitteilungen

Die Nachrichtenschleife in die `Run` Memberfunktion der Klasse `CWinApp` ruft in der Warteschlange Nachrichten, die durch verschiedene Ereignisse generiert. Klickt der Benutzer die Maus, sendet Windows beispielsweise mehrere mausbezogenen-Meldungen, z. B. WM_LBUTTONDOWN, wenn die linke Maustaste gedrückt wird und WM_LBUTTONUP, wenn die linke Maustaste losgelassen wird. Die Framework Implementierung der Meldungsschleife Anwendung sendet die Nachricht an das entsprechende Fenster.

Die wichtigsten Kategorien von Nachrichten werden in beschrieben [Meldungskategorien](../mfc/message-categories.md).

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

