---
title: Stile der Schieberegler-Steuerelemente
ms.date: 11/04/2016
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
ms.openlocfilehash: c6765445552826b71cca278c1fbbc66e500cb75a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307400"
---
# <a name="slider-control-styles"></a>Stile der Schieberegler-Steuerelemente

Schieberegler-Steuerelemente ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) haben eine vertikale oder horizontale Ausrichtung. Sie können die Teilstriche auf einer Seite, haben sowohl Seiten oder keines von beiden. Sie können auch verwendet werden, um einen Bereich aufeinander folgender Werte anzugeben. Mithilfe von Slider-Steuerelement-Stile, die Sie angeben, wenn Sie das Schieberegler-Steuerelement erstellen, werden diese Eigenschaften gesteuert.

Die Formate TBS_HORZ und TBS_VERT Bestimmen der Ausrichtung des Schieberegler-Steuerelements. Wenn Sie keine Ausrichtung angeben, wird das Schieberegler-Steuerelement horizontal ausgerichtet.

Styl TBS_AUTOTICKS erstellt ein Schieberegler-Steuerelement, das ein Teilstrichs für jedes Inkrement in der Wertebereich hat. Die Teilstriche werden automatisch hinzugefügt, beim Aufrufen der [SetRange](../mfc/reference/csliderctrl-class.md#setrange) Member-Funktion. Wenn Sie keine TBS_AUTOTICKS angeben, können Member-Funktionen, z. B. [SetTic](../mfc/reference/csliderctrl-class.md#settic) und [Memberfunktion SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), um anzugeben, die Positionen der Teilstriche. Um ein Schieberegler-Steuerelement zu erstellen, die nicht die Teilstriche angezeigt wird, können Sie den Stil TBS_NOTICKS verwenden.

Sie können die Teilstriche auf einer oder beide Seiten des Schieberegler-Steuerelements anzeigen. Für die horizontale Schieberegler-Steuerelemente können Sie den Stil TBS_BOTTOM oder das TBS_TOP angeben. Für den vertikalen Schieberegler-Steuerelemente können Sie den Stil TBS_RIGHT oder TBS_LEFT angeben. (TBS_BOTTOM und TBS_RIGHT sind die Standardeinstellungen.) Geben Sie für die Teilstriche auf beiden Seiten des Schieberegler-Steuerelements in alle Ausrichtung das TBS_BOTH-Format an.

Ein Schieberegler-Steuerelement kann einen Auswahlbereich angezeigt werden, nur dann, wenn Sie den Stil TBS_ENABLESELRANGE angeben, bei der Erstellung. Wenn ein Schieberegler-Steuerelement dieses Format aufweist, wird die Teilstriche an den Stellen Anfangs- und Endposition eines Bereichs Auswahl werden als Dreiecke (anstelle von senkrechte Striche) angezeigt, und der Auswahlbereich wird hervorgehoben. Beispielsweise können Auswahl Bereiche in einer einfachen Anwendung für die zeitplanung nützlich. Der Benutzer kann einen Bereich von Stunden an einem Tag zum Identifizieren des geplanten Zeitpunkt für Teilstriche auswählen.

Standardmäßig ändert sich die Länge des ein Schieberegler Steuerelement als die Auswahl geändert. Verfügt das Schieberegler-Steuerelement den TBS_FIXEDLENGTH-Stil, bleibt die Länge des Schiebereglers gleich, auch wenn der Auswahlbereich ändert. Ein Schiebereglersteuerelement, das dem TBS_NOTHUMB-Format enthält, umfasst keinen Schieberegler.

## <a name="see-also"></a>Siehe auch

[Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
