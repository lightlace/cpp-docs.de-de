---
title: Verwenden eines Abkürzungstasten-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
ms.openlocfilehash: 335489011076b1e30a9c36720a3bf2e94c7918b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542193"
---
# <a name="using-a-hot-key-control"></a>Verwenden eines Abkürzungstasten-Steuerelements

Typische Nutzung eines Abkürzungstasten-Steuerelements basiert auf dem folgenden Muster:

- Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, erfolgt die Erstellung automatisch, wenn das Dialogfeld erstellt wird. (Sollten Ihnen eine [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) Member in der Dialogfeldklasse, die die Abkürzungstasten-Steuerelements entsprechen.) Alternativ können Sie die [erstellen](../mfc/reference/chotkeyctrl-class.md#create) Member-Funktion, um das Steuerelement als untergeordnetes Fenster von einem beliebigen Fenster zu erstellen.

- Wenn Sie einen Standardwert für das Steuerelement festlegen möchten, rufen Sie die [Memberfunktion SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) Member-Funktion. Wenn Sie bestimmte UMSCHALT-Status nicht zulassen möchten, rufen Sie [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules). Für Steuerelemente in einem Dialogfeld, ist ein guter Zeitpunkt, zu diesem Zweck das Dialogfeld des [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Funktion.

- Der Benutzer interagiert mit dem Steuerelement, indem Sie die Tastenkombination drücken, wenn die Abkürzungstasten-Steuerelement den Fokus besitzt. Der Benutzer gibt dann irgendwie an, dass diese Aufgabe abgeschlossen ist, vielleicht ist durch Klicken auf eine Schaltfläche im Dialogfeld.

- Wenn Ihr Programm benachrichtigt wird, dass der Benutzer die Zugriffstaste ausgewählt hat, sollten sie die Member-Funktion verwenden [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) zum Abrufen der virtuelle Taste und UMSCHALT-Status-Werte aus der Abkürzungstasten-Steuerelements.

- Sobald Sie wissen, was vom Benutzer ausgewählten Schlüssel, können Sie festlegen, dass die Abkürzungstaste mit einer der beschriebenen Methoden [Festlegen einer Abkürzungstaste](../mfc/setting-a-hot-key.md).

- Wenn die Abkürzungstasten-Steuerelements in einem Dialogfeld wird es und die `CHotKeyCtrl` Objekt wird automatisch zerstört. Wenn nicht der Fall, Sie sicherstellen, dass sowohl das Steuerelement müssen und die `CHotKeyCtrl` Objekt ordnungsgemäß zerstört werden.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

