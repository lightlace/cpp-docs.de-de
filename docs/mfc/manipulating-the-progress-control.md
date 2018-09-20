---
title: Bearbeiten des Statussteuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fe784dfd63ec5c27a3695df3e6bc42ae0de2f7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416772"
---
# <a name="manipulating-the-progress-control"></a>Bearbeiten des Statussteuerelements

Es gibt drei Möglichkeiten zum Ändern der aktuellen Position des ein Statussteuerelement ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)).

- Die Position kann durch eine Menge von vordefinierten Inkrement geändert werden.

- Die Position kann durch einen willkürlichen Zeitraum geändert werden.

- Die Position kann auf einen bestimmten Wert geändert werden.

### <a name="to-change-the-position-by-a-preset-amount"></a>Um die Position, um einen vordefinierten Wert ändern

1. Verwenden der [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) Memberfunktion versucht, die die Schrittweite festlegen. Standardmäßig ist dieser Wert 10. Dieser Wert wird in der Regel als eine der anfänglichen Einstellungen für das Steuerelement festgelegt. Step-Wert kann negativ sein.

1. Verwenden der [StepIt](../mfc/reference/cprogressctrl-class.md#stepit) Memberfunktion versucht, die die Position zu erhöhen. Dies bewirkt, dass das Steuerelement selbst neu zeichnet.

    > [!NOTE]
    >  `StepIt` führt dazu, dass die Position, um zu umschließen. Angenommen, einen Bereich von 1 -100, einen Schritt von 20 und eine Position des 90 `StepIt` wird die Position auf 10 festgelegt.

### <a name="to-change-the-position-by-an-arbitrary-amount"></a>So ändern Sie die Position von einer beliebigen Anzahl

1. Verwenden der [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos) Member-Funktion, um die Position ändern. `OffsetPos` negative Werte werden akzeptiert werden.

    > [!NOTE]
    >  `OffsetPos`, im Gegensatz zu `StepIt`, der die Position wird nicht umbrochen. Die neue Position wird angepasst, damit Sie um innerhalb des Bereichs zu bleiben.

### <a name="to-change-the-position-to-a-specific-value"></a>Um die Position auf einen bestimmten Wert ändern

1. Verwenden der [Memberfunktion SetPos](../mfc/reference/cprogressctrl-class.md#setpos) Memberfunktion versucht, die die Position auf einen bestimmten Wert festgelegt. Bei Bedarf wird angepasst, dass die neue Position innerhalb des Bereichs liegen.

In der Regel ist das Statussteuerelement ausschließlich für die Ausgabe verwendet. Verwenden Sie zum Abrufen der aktuellen Position ohne einen neuen Wert [GetPos](../mfc/reference/cprogressctrl-class.md#getpos).

## <a name="see-also"></a>Siehe auch

[Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

