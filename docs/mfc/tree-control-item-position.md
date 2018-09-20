---
title: Position eines Elements im Struktursteuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e24c21a8a44f09e9141b1763646d1a887bda158
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412092"
---
# <a name="tree-control-item-position"></a>Position eines Elements im Struktursteuerelement

Die Anfangsposition eines Elements festgelegt ist, wenn die Strukturansicht-Steuerelement das Element hinzugefügt wird ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) mithilfe der `InsertItem` Member-Funktion. Der Aufruf der Memberfunktion gibt das Handle des übergeordneten Elements und das Handle des Elements nach dem das neue Element eingefügt werden soll. Das zweite Handle muss entweder ein untergeordnetes Element des angegebenen übergeordneten Elements identifizieren oder einen der folgenden Werte: `TVI_FIRST`, `TVI_LAST`, oder `TVI_SORT`.

Wenn `TVI_FIRST` oder `TVI_LAST` angegeben ist, wird das Strukturansicht-Steuerelement platziert das neue Element am Anfang oder Ende des angegebenen übergeordneten Elements der Liste der untergeordneten Elemente. Wenn `TVI_SORT` angegeben ist, wird das Strukturansicht-Steuerelement fügt das neue Element in der Liste der untergeordneten Elemente in alphabetischer Reihenfolge basierend auf den Text, der den Elementnamen.

Sie können ein übergeordnetes Element der Liste der untergeordneten Elemente in alphabetischer Reihenfolge einfügen, durch den Aufruf der [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) Member-Funktion. Diese Funktion enthält einen Parameter, der angibt, ob alle Ebenen von untergeordneten Elementen, die aus dem angegebenen übergeordneten Element absteigender auch in alphabetischer Reihenfolge sortiert werden.

Die [SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb) Member-Funktion können Sie zum Sortieren von untergeordneten Elementen basierend auf Kriterien, die Sie definieren. Wenn Sie diese Funktion aufrufen, geben Sie eine anwendungsdefinierten Rückruffunktion, die das Strukturansicht-Steuerelement aufrufen können, wenn die relative Reihenfolge von zwei untergeordneten Elementen entschieden werden muss. Die Callback-Funktion empfängt zwei 32-Bit-Anwendung definierten Werte für die verglichenen Elemente und ein dritter 32-Bit-Wert, den Sie, beim Aufrufen von angeben `SortChildrenCB`.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

