---
title: Verwenden von CHotKeyCtrl
ms.date: 11/04/2016
f1_keywords:
- CHotKeyCtrl
helpviewer_keywords:
- keys, hot and CHotKeyCtrl
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
ms.openlocfilehash: bf6ad9c8ea1b1a66f5a8abbf61f78c942ffda2fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483771"
---
# <a name="using-chotkeyctrl"></a>Verwenden von CHotKeyCtrl

Eines Abkürzungstasten-Steuerelements, durch Klasse dargestellten [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), ist ein Fenster, in dem eine Textdarstellung der Tastenkombination angezeigt, das der Benutzer, z. B. STRG + UMSCHALT + Q eingibt. Er verwaltet auch eine interne Darstellung des Schlüssels in Form von einem virtuellem Tastencode und einen Satz von Flags, die den UMSCHALT-Status darstellen. Die Abkürzungstasten-Steuerelements wird nicht tatsächlich die Abkürzungstaste festgelegt – ausführen, bis das Programm ist. (Eine Liste der standardmäßige virtuelle Tastencodes, finden Sie in der Winuser.h.)

Verwenden eines Abkürzungstasten-Steuerelements zum Abrufen der Benutzereingabe für die Abkürzungstaste, einem Fenster oder Thread zugeordnet werden soll. Abkürzungstasten-Steuerelemente werden häufig in Dialogfeldern verwendet werden, wie z. B. möglicherweise angezeigt werden, wenn den Benutzer eine Abkürzungstaste zuweisen. Es ist Aufgabe des Programms, der Werte, die den aktiven Schlüssel aus der Abkürzungstasten-Steuerelements abgerufen und rufen Sie die entsprechenden Funktionen, um die Abkürzungstaste mit einem Fenster oder Thread zu verknüpfen.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Verwenden eines Abkürzungstasten-Steuerelements](../mfc/using-a-hot-key-control.md)

- [Festlegen einer Abkürzungstaste](../mfc/setting-a-hot-key.md)

- [Globale Abkürzungstasten](../mfc/global-hot-keys.md)

- [Threadspezifische Abkürzungstasten](../mfc/thread-specific-hot-keys.md)

## <a name="see-also"></a>Siehe auch

[Steuerelemente](../mfc/controls-mfc.md)

