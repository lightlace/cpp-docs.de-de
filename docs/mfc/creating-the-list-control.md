---
title: Erstellen des Listensteuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: 7b2cb47699339dd413dc1bfae7623069da56e7a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242249"
---
# <a name="creating-the-list-control"></a>Erstellen des Listensteuerelements

Wie das Listensteuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) erstellt wird, ob Sie das Steuerelement direkt verwenden oder Klasse hängt [CListView](../mfc/reference/clistview-class.md) stattdessen. Bei Verwendung von `CListView`, das Framework erstellt die Sicht als Teil der Reihenfolge der Dokumente und Ansichten. Erstellen die Listenansicht erstellt das Listensteuerelement auch (beide sind identisch). Das Steuerelement wird erstellt, in der Ansicht [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler-Funktion. In diesem Fall wird das Steuerelement anschließend bereit für das Hinzufügen von Elementen, die über einen Aufruf an [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl).

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>Verwenden von CListCtrl direkt in einem Dialogfeld

1. Der Dialog-Editor fügen Sie ein Listensteuerelement hinzu, um der Dialogfeldvorlagen-Ressource. Geben Sie die Steuerelement-ID.

1. Verwenden der [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md) zum Hinzufügen einer Membervariablen des Typs `CListCtrl` mit der Eigenschaft des Steuerelements. Sie können diesen Member Aufrufen `CListCtrl` Memberfunktionen.

1. Eigenschaftenfenster Handlerfunktionen in die Dialogfeldklasse zuordnen, bei jeder Liste steuerelementebenachrichtigung Sie Nachrichten verarbeiten müssen verwenden (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

1. In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), legen Sie die Formate für die `CListCtrl`. Finden Sie unter [Ändern der Stile von Listensteuerelementen](../mfc/changing-list-control-styles.md). Dies bestimmt die Art von "View" erhalten Sie in das Steuerelement, auch wenn Sie die Ansicht später ändern können.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>Zum Verwenden von CListCtrl in einem nicht-Dialogfenster

1. Definieren Sie das Steuerelement in der Ansicht oder Fenster-Klasse.

1. Aufrufen des Steuerelements [erstellen](../mfc/reference/clistctrl-class.md#create) Memberfunktion, möglicherweise in [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), möglicherweise so frühzeitig wie des übergeordnete Fensters [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler-Funktion (Wenn Sie sind Erstellen von Unterklassen für das Steuerelement). Legen Sie die Formate für das Steuerelement.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
