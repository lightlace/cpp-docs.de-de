---
title: Behandeln der TTN_NEEDTEXT-Benachrichtigung für QuickInfos
ms.date: 11/04/2016
f1_keywords:
- TTN_NEEDTEXT
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
ms.openlocfilehash: 1dd73364b0b67e9ca3e7e47b172cc54db88aaba4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603631"
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>Behandeln der TTN_NEEDTEXT-Benachrichtigung für QuickInfos

Als Teil des [QuickInfos](../mfc/enabling-tool-tips.md), Sie behandeln die **TTN_NEEDTEXT** Nachricht, indem Sie den folgenden Eintrag zur meldungszuordnung Ihres Besitzerfensters hinzufügen:

[!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]

*memberFxn*<br/>
Die Memberfunktion aufgerufen werden, wenn der Text für diese Schaltfläche benötigt wird.

Beachten Sie, dass die ID der QuickInfo immer 0.

Deklarieren Sie die Handlerfunktion wird in der Klassendefinition wie folgt:

[!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]

die kursiv Parameter lauten:

*ID*<br/>
Der Bezeichner des Steuerelements, das die Benachrichtigung gesendet. Nicht verwendet. Die Steuerelement-Id stammt aus dem **NMHDR** Struktur.

*pNMHDR*<br/>
Ein Zeiger auf die [NMTTDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagnmttdispinfoa) Struktur. Diese Struktur wird ebenfalls erläutert. im weiteren [der TOOLTIPTEXT-Struktur](../mfc/tooltiptext-structure.md).

*pResult*<br/>
Ein Zeiger auf Ergebniscode können Sie festlegen, bevor Sie zurückkehren. **TTN_NEEDTEXT** Handler können ignorieren die *pResult* Parameter.

Als Beispiel für eine Formularansicht Benachrichtigungshandler:

[!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]

Rufen Sie `EnableToolTips` (dieses Fragment entnommen `OnInitDialog`):

[!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]

## <a name="see-also"></a>Siehe auch

[QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

