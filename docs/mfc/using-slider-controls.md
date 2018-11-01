---
title: Verwenden von Schieberegler-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
ms.openlocfilehash: 7bb5bda4a7b85ea8bb852649b20f10f0c4693188
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533561"
---
# <a name="using-slider-controls"></a>Verwenden von Schieberegler-Steuerelementen

Typische Verwendung des Schieberegler-Steuerelements basiert auf dem folgenden Muster:

- Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, erfolgt die Erstellung automatisch, wenn das Dialogfeld erstellt wird. (Sollten Ihnen eine [CSliderCtrl](../mfc/reference/csliderctrl-class.md) Member in der Dialogfeldklasse, die das Schieberegler-Steuerelement entspricht.) Alternativ können Sie die [erstellen](../mfc/reference/csliderctrl-class.md#create) Member-Funktion, um das Steuerelement als untergeordnetes Fenster von einem beliebigen Fenster zu erstellen.

- Rufen Sie die verschiedenen Satz Memberfunktionen, um Werte für das Steuerelement festzulegen. Änderungen, die Sie vornehmen können, enthalten die minimalen und maximalen Positionen für den Schieberegler festlegen, Teilstriche zu zeichnen, einen Auswahlbereich festlegen und Neupositionieren von den Schieberegler. Für Steuerelemente in einem Dialogfeld, ist ein guter Zeitpunkt, zu diesem Zweck die im Dialogfeld [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Funktion.

- Während der Benutzer mit dem Steuerelement interagiert, sendet er die verschiedenen Benachrichtigungen. Sie können den Wert des Schiebereglers aus dem Steuerelement extrahieren, durch den Aufruf der [GetPos](../mfc/reference/csliderctrl-class.md#getpos) Member-Funktion.

- Wenn Sie mit dem Steuerelement fertig sind, müssen Sie sicherstellen, dass es ordnungsgemäß zerstört wird. Das Schieberegler-Steuerelement in einem Dialogfeld, ist es und die `CSliderCtrl` Objekt wird automatisch zerstört. Wenn nicht der Fall, Sie sicherstellen, dass sowohl das Steuerelement müssen und die `CSliderCtrl` Objekt ordnungsgemäß zerstört werden.

## <a name="see-also"></a>Siehe auch

[Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

