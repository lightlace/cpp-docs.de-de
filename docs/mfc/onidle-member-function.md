---
title: OnIdle-Memberfunktion
ms.date: 11/19/2018
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: c7cdd5cd2327be1b90e7fdb3694353acf8adcafe
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304438"
---
# <a name="onidle-member-function"></a>OnIdle-Memberfunktion

Wenn Sie keine Windows-Meldungen verarbeitet werden, um das Framework Ruft die [CWinApp](../mfc/reference/cwinapp-class.md) Memberfunktion [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (beschrieben in der MFC-Bibliothek-Referenz).

Außer Kraft setzen `OnIdle` Hintergrundaufgaben ausführen. Die Standard-Version aktualisiert den Zustand der Objekte der Benutzeroberfläche wie Symbolleisten-Schaltflächen und führt die Bereinigung der temporären Objekte, die vom Framework im Verlauf der Vorgänge erstellt. Die folgende Abbildung veranschaulicht, wie die Nachrichtenschleife aufruft `OnIdle` Wenn in der Warteschlange keine Nachrichten vorhanden sind.

![Message Loop-Prozess](../mfc/media/vc387c1.gif "nachrichtenschleifenprozess") <br/>
Nachrichtenschleife

Weitere Informationen, was Sie in der Leerlaufschleife tun können, finden Sie unter [Leerlaufschleifen-Verarbeitung](../mfc/idle-loop-processing.md).

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsserver-Klasse](../mfc/cwinapp-the-application-class.md)
