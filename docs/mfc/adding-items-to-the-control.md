---
title: Hinzufügen von Elementen zum Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 6c03be6f04746ec2e3146916d72cad637a204187
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509326"
---
# <a name="adding-items-to-the-control"></a>Hinzufügen von Elementen zum Steuerelement

Um dem Listen Steuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) Elemente hinzuzufügen, müssen Sie eine von mehreren Versionen der [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) -Member-Funktion aufzurufen, je nachdem, welche Informationen Sie besitzen. Eine Version übernimmt eine [lvitem](/windows/win32/api/commctrl/ns-commctrl-lvitemw) -Struktur, die Sie vorbereiten. Da die `LVITEM` Struktur zahlreiche Member enthält, haben Sie eine bessere Kontrolle über die Attribute des Listen Steuerelement Elements.

Zwei wichtige Member (hinsichtlich der Berichtsansicht) `LVITEM` der-Struktur sind die `iItem` -und- `iSubItem` Member. Der `iItem` -Member ist der null basierte Index des Elements, auf das die-Struktur verweist, `iSubItem` und der-Member ist der einsbasierte Index eines unter Elements, oder 0 (null), wenn die Strukturinformationen zu einem Element enthält. Mit diesen beiden Membern legen Sie den Typ und den Wert der Unterelement Informationen fest, die angezeigt werden, wenn sich das Listen Steuerelement in der Berichtsansicht befindet. Weitere Informationen finden Sie unter [CListCtrl:: System](../mfc/reference/clistctrl-class.md#setitem)Item.

Zusätzliche Member geben Text-, Symbol-, Zustands-und Elementdaten des Elements an. "Elementdaten" ist ein Anwendungs definierter Wert, der einem Listen Ansichts Element zugeordnet ist. Weitere Informationen `LVITEM` zur-Struktur finden Sie unter [CListCtrl:: GetItem](../mfc/reference/clistctrl-class.md#getitem).

Andere Versionen von `InsertItem` nehmen einen oder mehrere separate Werte auf, die den Elementen in `LVITEM` der Struktur entsprechen, sodass Sie nur die Member initialisieren können, die Sie unterstützen möchten. Im Allgemeinen verwaltet das Listen Steuerelement den Speicher für Listenelemente, Sie können jedoch einige der Informationen in der Anwendung speichern, indem Sie "Rückruf Elemente" verwenden. Weitere Informationen finden Sie unter [Rückruf Elemente und Rückruf Maske](../mfc/callback-items-and-the-callback-mask.md) in diesem Thema und [Rückruf Elemente und die Rückruf Maske](/windows/win32/Controls/using-list-view-controls) in der Windows SDK.

Weitere Informationen finden Sie unter [Hinzufügen von Listen Ansichts Elementen und unter Elementen](/windows/win32/Controls/using-list-view-controls).

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
