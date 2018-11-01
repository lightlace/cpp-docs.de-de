---
title: Wechseln der Auswahl in einem Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: bd3ade31ce1e41481943659ba9a8ef8dd77117fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592715"
---
# <a name="tree-control-item-selection"></a>Wechseln der Auswahl in einem Struktursteuerelement

Wenn die Auswahl ändert sich von einem Element zu einem anderen ein Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sendet [TVN_SELCHANGING](/windows/desktop/Controls/tvn-selchanging) und [eine TVN_SELCHANGED](/windows/desktop/Controls/tvn-selchanged) benachrichtigungsmeldungen. Beide Benachrichtigungen enthalten einen Wert, der angibt, ob die Änderung das Ergebnis klicken mit der Maus oder Drücken einer Taste ist. Die Benachrichtigungen umfassen auch Informationen über das Element, das die Auswahl Zustand wechselt und das Element, das die Auswahl entfernt wird. Sie können diese Informationen verwenden, Elementattribute festlegen, die abhängig von den Auswahlzustand des Elements. Zurückgeben von **"true"** als Reaktion auf `TVN_SELCHANGING` wird verhindert, dass die Auswahl ändern; zurückgeben **"false"** ermöglicht die Änderung.

Eine Anwendung kann die Auswahl ändern, durch den Aufruf der [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

