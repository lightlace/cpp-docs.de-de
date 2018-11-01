---
title: Verarbeiten von Benachrichtigungsmeldungen des Registersteuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: 75b19033a31d707fcc87c1b5c824acffca725c96
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441968"
---
# <a name="processing-tab-control-notification-messages"></a>Verarbeiten von Benachrichtigungsmeldungen des Registersteuerelements

Da der Benutzer klicken Sie auf Registerkarten oder Schaltflächen, das Registerkarten-Steuerelement ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) sendet benachrichtigungsmeldungen an das übergeordnete Fenster. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Klickt der Benutzer eine Registerkarte, sollten Sie beispielsweise Daten des Steuerelements auf der Seite vor der Anzeige die Voreinstellung.

Prozess WM_NOTIFY-Meldungen aus dem Registerkarten-Steuerelement in Ihrer Klasse Ansichts- oder Dialogfeldobjekt. Verwenden Sie das Fenster "Eigenschaften" zum Erstellen einer [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) Handlerfunktion mit einer Switch-Anweisung basierend auf der Nachricht behandelt wird. Eine Liste der Benachrichtigungen ein Registerkarten-Steuerelement an sein übergeordnetes Fenster senden kann, finden Sie unter den **Benachrichtigungen** Abschnitt [Registerkarte Steuerelementverweis](https://msdn.microsoft.com/library/windows/desktop/bb760548) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

