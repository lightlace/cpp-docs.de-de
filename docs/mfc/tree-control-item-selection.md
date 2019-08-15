---
title: Wechseln der Auswahl in einem Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: 07c7b673e0f9029f8ece928b0ab17760b3863cc7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513337"
---
# <a name="tree-control-item-selection"></a>Wechseln der Auswahl in einem Struktursteuerelement

Wenn sich die Auswahl von einem Element in ein anderes ändert, sendet ein Struktur Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) [TVN_SELCHANGING](/windows/win32/Controls/tvn-selchanging) -und [TVN_SELCHANGED](/windows/win32/Controls/tvn-selchanged) -Benachrichtigungs Meldungen. Beide Benachrichtigungen enthalten einen Wert, der angibt, ob es sich bei der Änderung um das Ergebnis eines Mausklicks oder eines Tastatur Schlags handelt. Die Benachrichtigungen enthalten außerdem Informationen über das Element, das die Auswahl erhält, und das Element, das die Auswahl verliert. Mit diesen Informationen können Sie Element Attribute festlegen, die vom Auswahl Zustand des Elements abhängen. Wenn "true" in `TVN_SELCHANGING` Reaktion auf " **true** " zurückgegeben wird, kann die Auswahl nicht geändert werden

Eine Anwendung kann die Auswahl durch Aufrufen der [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) -Member-Funktion ändern.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
