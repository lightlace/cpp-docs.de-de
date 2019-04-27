---
title: Erstellen des Headersteuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
ms.openlocfilehash: 669b13cf566f24bfcd5a29ae41af1cdb90513f73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242314"
---
# <a name="creating-the-header-control"></a>Erstellen des Headersteuerelements

(Obwohl Sie ein Listensteuerelement, einschließlich einem Kopfzeilen-Steuerelement hinzufügen können), ist das Kopfzeilen-Steuerelement nicht direkt im Dialog-Editor verfügbar sind.

### <a name="to-put-a-header-control-in-a-dialog-box"></a>Einfügen von einem Kopfzeilen-Steuerelement in einem Dialogfeld

1. Betten Sie manuell eine Membervariable des Typs [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) in der Dialogfeldklasse.

1. In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), erstellen, und legen Sie die Formate für die `CHeaderCtrl`, positionieren Sie es, und zeigen Sie es.

1. Das Kopfzeilen-Steuerelement Elemente hinzugefügt.

1. Verwendet im Eigenschaftenfenster in Handlerfunktionen in die Dialogfeldklasse zuordnen, für das Kopfzeilen-Steuerelement Benachrichtigungen angezeigt werden, behandeln müssen (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Einfügen von einem Kopfzeilen-Steuerelement in einer Ansicht (nicht in einer CListView)

1. Einbetten einer [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) Objekt in Ihrer Ansichtsklasse.

1. Stil und position anzeigen Steuerelementfensters der Header in der Ansicht [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) Member-Funktion.

1. Das Kopfzeilen-Steuerelement Elemente hinzugefügt.

1. Verwendet im Eigenschaftenfenster in Handlerfunktionen in der Ansichtsklasse zuordnen, für das Kopfzeilen-Steuerelement Benachrichtigungen angezeigt werden, behandeln müssen (finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)).

In beiden Fällen wird das eingebettete Steuerelement-Objekt erstellt, wenn die Ansichts- oder Dialogfeldobjekt-Objekt erstellt wird. Sie aufrufen müssen [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md#create) um das Fenster des Steuerelements zu erstellen. Aufrufen, um das Steuerelement zu positionieren, [CHeaderCtrl:: Layout](../mfc/reference/cheaderctrl-class.md#layout) anfängliche Größe und Position des Steuerelements zu bestimmen und [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) auf die Position festgelegt werden sollen. Klicken Sie dann Elemente hinzufügen, wie in beschrieben [Hinzufügen von Elementen zum Headersteuerelement](../mfc/adding-items-to-the-header-control.md).

Weitere Informationen finden Sie unter [einem Kopfzeilen-Steuerelement erstellen](/windows/desktop/Controls/header-controls) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
