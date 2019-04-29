---
title: Position eines Elements im Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
ms.openlocfilehash: 238cb40319d28a53592a594a72947f400720f935
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392478"
---
# <a name="tree-control-item-position"></a>Position eines Elements im Struktursteuerelement

Die Anfangsposition eines Elements festgelegt ist, wenn die Strukturansicht-Steuerelement das Element hinzugefügt wird ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) mithilfe der `InsertItem` Member-Funktion. Der Aufruf der Memberfunktion gibt das Handle des übergeordneten Elements und das Handle des Elements nach dem das neue Element eingefügt werden soll. Das zweite Handle muss entweder ein untergeordnetes Element des angegebenen übergeordneten Elements identifizieren oder einen der folgenden Werte: `TVI_FIRST`, `TVI_LAST`, oder `TVI_SORT`.

Wenn `TVI_FIRST` oder `TVI_LAST` angegeben ist, wird das Strukturansicht-Steuerelement platziert das neue Element am Anfang oder Ende des angegebenen übergeordneten Elements der Liste der untergeordneten Elemente. Wenn `TVI_SORT` angegeben ist, wird das Strukturansicht-Steuerelement fügt das neue Element in der Liste der untergeordneten Elemente in alphabetischer Reihenfolge basierend auf den Text, der den Elementnamen.

Sie können ein übergeordnetes Element der Liste der untergeordneten Elemente in alphabetischer Reihenfolge einfügen, durch den Aufruf der [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) Member-Funktion. Diese Funktion enthält einen Parameter, der angibt, ob alle Ebenen von untergeordneten Elementen, die aus dem angegebenen übergeordneten Element absteigender auch in alphabetischer Reihenfolge sortiert werden.

Die [SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) Member-Funktion können Sie zum Sortieren von untergeordneten Elementen basierend auf Kriterien, die Sie definieren. Wenn Sie diese Funktion aufrufen, geben Sie eine anwendungsdefinierten Rückruffunktion, die das Strukturansicht-Steuerelement aufrufen können, wenn die relative Reihenfolge von zwei untergeordneten Elementen entschieden werden muss. Die Callback-Funktion empfängt zwei 32-Bit-Anwendung definierten Werte für die verglichenen Elemente und ein dritter 32-Bit-Wert, den Sie, beim Aufrufen von angeben `SortChildrenCB`.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
