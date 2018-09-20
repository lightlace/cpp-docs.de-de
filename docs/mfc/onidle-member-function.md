---
title: OnIdle-Memberfunktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b334a4561af40b69bc367ab5b1129afa8fb29ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377294"
---
# <a name="onidle-member-function"></a>OnIdle-Memberfunktion

Wenn Sie keine Windows-Meldungen verarbeitet werden, um das Framework Ruft die [CWinApp](../mfc/reference/cwinapp-class.md) Memberfunktion [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (beschrieben in der MFC-Bibliothek-Referenz).

Außer Kraft setzen `OnIdle` Hintergrundaufgaben ausführen. Die Standard-Version aktualisiert den Zustand der Objekte der Benutzeroberfläche wie Symbolleisten-Schaltflächen und führt die Bereinigung der temporären Objekte, die vom Framework im Verlauf der Vorgänge erstellt. Die folgende Abbildung veranschaulicht, wie die Nachrichtenschleife aufruft `OnIdle` Wenn in der Warteschlange keine Nachrichten vorhanden sind.

![Message Loop-Prozess](../mfc/media/vc387c1.gif "vc387c1") der Nachrichtenschleife

Weitere Informationen, was Sie in der Leerlaufschleife tun können, finden Sie unter [Leerlaufschleifen-Verarbeitung](../mfc/idle-loop-processing.md).

## <a name="see-also"></a>Siehe auch

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
