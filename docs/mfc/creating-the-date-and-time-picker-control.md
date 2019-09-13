---
title: Erstellen des Steuerelements für Datum und Uhrzeit
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
ms.openlocfilehash: de9baf63577d163b82da1c5977a6ccba6539c73a
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907599"
---
# <a name="creating-the-date-and-time-picker-control"></a>Erstellen des Steuerelements für Datum und Uhrzeit

Wie das Steuerelement für die Datums-und Uhrzeit Auswahl erstellt wird, hängt davon ab, ob Sie das Steuerelement in einem Dialogfeld verwenden oder es in einem nicht Dialogfeld erstellen.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>So verwenden Sie CDateTimeCtrl direkt in einem Dialogfeld

1. Fügen Sie im Dialog-Editor der Dialogfeld Vorlagen-Ressource ein Steuerelement für die Datums-und Uhrzeit Auswahl hinzu. Gibt die Steuerelement-ID an.

1. Geben Sie im Dialogfeld "Eigenschaften" des Steuer Elements für die Datums-und Uhrzeit Auswahl alle benötigten Stile an.

1. Verwenden Sie den [Assistenten zum Hinzufügen](../ide/adding-a-member-variable-visual-cpp.md) von Element Variablen, um eine Member-Variable vom Typ [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) mit der Control-Eigenschaft hinzuzufügen. Sie können diesen Member verwenden, um `CDateTimeCtrl` Member-Funktionen aufzurufen.

1. Verwenden Sie den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um Handlerfunktionen in der Dialogfeld Klasse für beliebige [Benachrichtigungs](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) Meldungen für Datums-und Zeitauswahl Steuerelemente zuzuordnen, die Sie behandeln müssen (siehe zuordnen [von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md))

1. Legen Sie in [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)alle zusätzlichen Stile für das `CDateTimeCtrl` -Objekt fest.

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>So verwenden Sie CDateTimeCtrl in einem nicht-Dialogfenster

1. Deklarieren Sie das Steuerelement in der Ansicht oder in der Fenster Klasse.

1. Rufen Sie die [Create](../mfc/reference/ctabctrl-class.md#create) Member-Funktion des Steuer Elements (möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)) auf, möglicherweise so früh wie die [OnCreate](../mfc/reference/cwnd-class.md#oncreate) -Handlerfunktion des übergeordneten Fensters (wenn Sie das Steuerelement Unterklassen). Legen Sie die Stile für das-Steuerelement fest.

## <a name="see-also"></a>Siehe auch

[Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
