---
title: Einstellungen für das Statussteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
ms.openlocfilehash: 1960b15c2f76d7cbfc9f249a77481b795e6a27ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307678"
---
# <a name="settings-for-the-progress-control"></a>Einstellungen für das Statussteuerelement

Die grundlegenden Einstellungen für das Statussteuerelement ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) sind der Bereich und die aktuelle Position. Den Bereich darstellt, die gesamte Dauer des Vorgangs. Die aktuelle Position darstellt, den Status, die Ihre Anwendung bis zum Abschluss der Operation hat. Alle Änderungen an den Bereich oder die Position dazu führen, dass das Statussteuerelement gezeichnet wird.

Standardmäßig wird der Bereich festgelegt, der 0 - 100, und die ursprüngliche Position auf 0 festgelegt ist. Verwenden Sie zum Abrufen der aktuellen bereichseinstellungen für das Statussteuerelement der [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) Member-Funktion. Verwenden Sie zum Ändern des Bereichs der [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) Member-Funktion.

Verwenden Sie zum Festlegen der Position [Memberfunktion SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Verwenden Sie zum Abrufen der aktuellen Position ohne einen neuen Wert [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Beispielsweise empfiehlt es sich um einfach auf den Status des aktuellen Vorgangs abzufragen.

Verwenden Sie zum Ausführen die aktuelle Position des das Statussteuerelement [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Verwenden Sie zum Festlegen der Größe der einzelnen Schritte [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)

## <a name="see-also"></a>Siehe auch

[Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
