---
title: Erstellen des Listensteuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: f1c5d8db93421e1d3ae0e39aec82bdf0f5529f1f
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907926"
---
# <a name="creating-the-list-control"></a>Erstellen des Listensteuerelements

Die Art und Weise, wie das Listen Steuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) erstellt wird, hängt davon ab, ob Sie das Steuerelement direkt verwenden oder stattdessen die Klasse [CListView](../mfc/reference/clistview-class.md) verwenden. Wenn Sie verwenden `CListView`, erstellt das Framework die Sicht als Teil der Dokument-/Ansicht-Erstellungs-Sequenz. Wenn Sie die Listenansicht erstellen, wird auch das Listen Steuerelement erstellt (beide sind identisch). Das-Steuerelement wird in der [OnCreate](../mfc/reference/cwnd-class.md#oncreate) -Handlerfunktion der Sicht erstellt. In diesem Fall kann das Steuerelement mithilfe eines Aufrufens von [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl)Elemente hinzufügen.

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>So verwenden Sie CListCtrl direkt in einem Dialogfeld

1. Fügen Sie im Dialog-Editor der Dialogfeld Vorlagen Ressource ein Listen Steuerelement hinzu. Gibt die Steuerelement-ID an.

1. Verwenden Sie den [Assistenten zum Hinzufügen](../ide/adding-a-member-variable-visual-cpp.md) von Element Variablen, um eine `CListCtrl` Element Variable vom Typ mit der Control-Eigenschaft hinzuzufügen. Sie können diesen Member verwenden, um `CListCtrl` Member-Funktionen aufzurufen.

1. Verwenden Sie den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um Handlerfunktionen in der Dialogfeld Klasse für beliebige Benachrichtigungs Meldungen für das Listen Steuerelement zuzuordnen, die Sie behandeln müssen. (siehe [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md))

1. Legen Sie in [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)die Stile für das `CListCtrl`fest. Siehe [Ändern von Listen Steuerelement Stilen](../mfc/changing-list-control-styles.md). Dies bestimmt die Art der "Ansicht", die Sie im Steuerelement erhalten, obwohl Sie die Ansicht später ändern können.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>So verwenden Sie CListCtrl in einem nicht Dialogfeld Fenster

1. Definieren Sie das Steuerelement in der Ansicht oder in der Fenster Klasse.

1. Rufen Sie die [Create](../mfc/reference/clistctrl-class.md#create) Member-Funktion des Steuer Elements (möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)) auf, möglicherweise so früh wie die [OnCreate](../mfc/reference/cwnd-class.md#oncreate) -Handlerfunktion des übergeordneten Fensters (wenn Sie das Steuerelement Unterklassen). Legen Sie die Stile für das-Steuerelement fest.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
