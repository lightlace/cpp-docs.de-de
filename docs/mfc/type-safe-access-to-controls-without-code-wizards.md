---
title: Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
ms.openlocfilehash: 2b337aa28d5fdf061d1db4b5cf66303688ef5bf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501711"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten

Der erste Ansatz zum Erstellen von typsicheren Zugriff auf Steuerelemente verwendet eine Inline-Member-Funktion, um den Rückgabetyp der Klasse umgewandelt `CWnd`des `GetDlgItem` Memberfunktion für die entsprechende C++-Steuerelementtyp, wie im folgenden Beispiel:

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

Sie können diese Member-Funktion klicken Sie dann auf das Steuerelement in einer typsicheren Weise mit Code wie den folgenden verwenden:

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>Siehe auch

[Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten](../mfc/type-safe-access-to-controls-with-code-wizards.md)

