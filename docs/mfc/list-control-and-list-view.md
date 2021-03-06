---
title: Listensteuerelement und Listenansichtsteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
ms.openlocfilehash: 5c9612a22eab27d568c0dbb86d29ba031fe5985e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365326"
---
# <a name="list-control-and-list-view"></a>Listensteuerelement und Listenansichtsteuerelement

Der Einfachheit halber kapselt MFC Listensteuerelement gibt es zwei Möglichkeiten. Sie können die Steuerelemente aufgelistet:

- Direkt durch das Einbetten einer [CListCtrl](../mfc/reference/clistctrl-class.md) Objekt in einem Dialogfeldklasse.

- Indirekt mithilfe der Klasse [CListView](../mfc/reference/clistview-class.md).

`CListView` erleichtert Ihnen die in der MFC Dokument-/Ansichtarchitektur, kapseln das Steuerelement ein Listensteuerelement integrieren wie [CEditView](../mfc/reference/ceditview-class.md) kapselt ein Bearbeitungssteuerelement: füllt das Steuerelement die gesamte Oberfläche der MFC-Ansicht. (Die Ansicht *ist* das Steuerelement, umgewandelt in `CListView`.)

Ein `CListView` Objekt erbt die [CCtrlView](../mfc/reference/cctrlview-class.md) und Basis-Klassen und fügt eine Memberfunktion, um das zugrunde liegende Listensteuerelement abzurufen. Verwenden Sie Mitglieder anzeigen, um mit der Sicht als Sicht arbeiten. Verwenden der [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) Member-Funktion für den Zugriff auf das Listensteuerelement Member-Funktionen. Verwenden Sie diese Member zu:

- Fügen Sie hinzu, löschen Sie oder bearbeiten Sie "Elemente" in der Liste.

- Festlegen Sie oder rufen Sie der Liste der Attribute von Steuerelementen ab.

Abrufen eines Verweises auf die `CListCtrl` zugrunde liegende eine `CListView`, rufen Sie `GetListCtrl` aus Ihrer Listenansichtsklasse:

[!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]

Dieses Thema beschreibt die beiden Möglichkeiten, das Strukturelement-Steuerelement zu verwenden.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
