---
title: Struktur der Auswahl in einem | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa9c82a57ff8504c8e3eba7becff1e1cdccaae2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431566"
---
# <a name="tree-control-item-selection"></a>Wechseln der Auswahl in einem Struktursteuerelement

Wenn die Auswahl ändert sich von einem Element zu einem anderen ein Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sendet [TVN_SELCHANGING](/windows/desktop/Controls/tvn-selchanging) und [eine TVN_SELCHANGED](/windows/desktop/Controls/tvn-selchanged) benachrichtigungsmeldungen. Beide Benachrichtigungen enthalten einen Wert, der angibt, ob die Änderung das Ergebnis klicken mit der Maus oder Drücken einer Taste ist. Die Benachrichtigungen umfassen auch Informationen über das Element, das die Auswahl Zustand wechselt und das Element, das die Auswahl entfernt wird. Sie können diese Informationen verwenden, Elementattribute festlegen, die abhängig von den Auswahlzustand des Elements. Zurückgeben von **"true"** als Reaktion auf `TVN_SELCHANGING` wird verhindert, dass die Auswahl ändern; zurückgeben **"false"** ermöglicht die Änderung.

Eine Anwendung kann die Auswahl ändern, durch den Aufruf der [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

