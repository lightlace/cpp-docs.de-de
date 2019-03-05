---
title: 'MFC-ActiveX-Steuerelemente: Zurückgeben von Fehlercodes aus einer Methode'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
ms.openlocfilehash: 0800c1827c636dd81e2928e33c0ee2afde4c94ac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259138"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC-ActiveX-Steuerelemente: Zurückgeben von Fehlercodes aus einer Methode

In diesem Artikel wird beschrieben, wie zum Zurückgeben von Fehlercodes aus einem ActiveX-Steuerelementmethode wird.

Um anzugeben, dass innerhalb einer Methode ein Fehler aufgetreten ist, verwenden Sie die [ThrowError](../mfc/reference/colecontrol-class.md#throwerror) Member-Funktion, die einen SCODE (Statuscode:) als Parameter annimmt. Sie können einen vordefinierten SCODE oder definieren ein eigenes.

> [!NOTE]
>  `ThrowError` nur als Rückgabe einen Fehler aus, in einer Eigenschaft Get oder Set verwendet werden soll-Funktion oder ein Automation-Methode. Hierbei handelt es sich um das einzige Mal, die der entsprechenden Ausnahmehandler übergeben werden auf dem Stapel vorhanden.

Hilfsfunktionen vorhanden sind, für die am häufigsten verwendeten SCODEs, z. B. vordefinierte [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), und [COleControl::SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).

Eine Liste der vordefinierten SCODEs und Anweisungen zum Definieren von benutzerdefinierten SCODEs, finden Sie im Abschnitt [Behandeln von Fehlern in der ActiveX-Steuerelement](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX-Steuerelementen: Weiterführende Themen.

Weitere Informationen zum Melden von Ausnahmen in anderen Bereichen des Codes, finden Sie unter [COleControl:: FireError](../mfc/reference/colecontrol-class.md#fireerror) und im Abschnitt [Behandeln von Fehlern in der ActiveX-Steuerelement](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX-Steuerelementen: Weiterführende Themen.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)
