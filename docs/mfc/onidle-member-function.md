---
title: OnIdle-Memberfunktion
ms.date: 11/04/2016
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: 3d457c1675d5f5f3f88c67b1aac2d03509c21564
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662149"
---
# <a name="onidle-member-function"></a>OnIdle-Memberfunktion

Wenn Sie keine Windows-Meldungen verarbeitet werden, um das Framework Ruft die [CWinApp](../mfc/reference/cwinapp-class.md) Memberfunktion [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (beschrieben in der MFC-Bibliothek-Referenz).

Außer Kraft setzen `OnIdle` Hintergrundaufgaben ausführen. Die Standard-Version aktualisiert den Zustand der Objekte der Benutzeroberfläche wie Symbolleisten-Schaltflächen und führt die Bereinigung der temporären Objekte, die vom Framework im Verlauf der Vorgänge erstellt. Die folgende Abbildung veranschaulicht, wie die Nachrichtenschleife aufruft `OnIdle` Wenn in der Warteschlange keine Nachrichten vorhanden sind.

![Message Loop-Prozess](../mfc/media/vc387c1.gif "vc387c1") der Nachrichtenschleife

Weitere Informationen, was Sie in der Leerlaufschleife tun können, finden Sie unter [Leerlaufschleifen-Verarbeitung](../mfc/idle-loop-processing.md).

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
