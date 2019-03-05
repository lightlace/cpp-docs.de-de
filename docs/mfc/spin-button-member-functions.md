---
title: Memberfunktionen für das Drehfeldsteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
ms.openlocfilehash: 5ad6f529762e77e1cf1c00f41eea0add5d196fbb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298398"
---
# <a name="spin-button-member-functions"></a>Memberfunktionen für das Drehfeldsteuerelement

Es stehen mehrere Member-Funktionen für das Drehfeld-Steuerelement ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Verwenden Sie diese Funktionen so ändern Sie die folgenden Attribute von der Schaltfläche "starten".

- **Acceleration** können Sie die Rate, mit der die Position ändert, wenn der Benutzer die Pfeiltaste gedrückt hält, anpassen. Verwenden Sie zum Arbeiten mit Beschleunigung der [Memberfunktionen SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) und [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) Memberfunktionen.

- **Basis** Sie können ändern, dass die Basis (10 oder 16) verwendet, um die Position in der Beschriftung des Buddy-Fensters anzuzeigen. Verwenden Sie zum Arbeiten mit der Basis der [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) und [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) Memberfunktionen.

- **Buddy-Fenster** dynamisch lassen sich das Buddyfenster. Um abzufragen oder zu ändern, welches Steuerelement die Buddy-Fenster ist, verwenden Sie die [Memberfunktionen GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) und [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) Memberfunktionen.

- **Position** können Sie Abfragen und Ändern der Position. Verwenden, um arbeiten direkt mit der Position der [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) und [Memberfunktion SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) Memberfunktionen. Da die Beschriftung des Buddysteuerelements möglicherweise (z. B. im Fall geändert, dass sich das Buddy ein Bearbeitungssteuerelement ist) `GetPos` Ruft die aktuelle Beschriftung und die Position entsprechend angepasst.

- **Bereich** können Sie die maximalen und minimalen Positionen für das Drehfeld ändern. Standardmäßig ist das Maximum auf 0 festgelegt, und mindestens auf 100 festgelegt ist. Da das Standardmaximum kleiner als der minimale Standardwert ist, ist die Aktionen der Pfeilschaltflächen nicht intuitiv. In der Regel legen Sie den Bereich mithilfe der [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) Member-Funktion. Um die Verwendung des Bereichs abzufragen [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange).

## <a name="see-also"></a>Siehe auch

[Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
