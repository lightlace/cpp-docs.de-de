---
title: Verwenden eines Abkürzungstasten-Steuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be0d27016204724672c23f04fdee38f01b69e6a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372289"
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

