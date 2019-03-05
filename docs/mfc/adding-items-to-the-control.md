---
title: Hinzufügen von Elementen zum Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 88e008f06fb669db1c13872b1a58555eeb357d86
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304599"
---
# <a name="adding-items-to-the-control"></a>Hinzufügen von Elementen zum Steuerelement

Das Strukturelement-Steuerelement Elemente hinzugefügt ([CListCtrl](../mfc/reference/clistctrl-class.md)), rufen Sie eine der mehrere Versionen der [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) Member-Funktion, je nachdem welche Informationen Sie. Eine Version übernimmt einen [LV_ITEM](/windows/desktop/api/commctrl/ns-commctrl-taglvitema) Struktur, die Sie vorbereiten. Da die `LV_ITEM` Struktur enthält zahlreiche Elemente, stehen Ihnen mehr Kontrolle über die Attribute des Elements des Listensteuerelements.

Zwei wichtige Member (in Bezug auf die Berichtsansicht) von der `LV_ITEM` Struktur werden die `iItem` und `iSubItem` Member. Die `iItem` Member ist der nullbasierte Index des Elements verweist auf die Struktur und die `iSubItem` Member ist der einsbasierte Index ein Unterelement oder 0 (null), wenn die Struktur Informationen über ein Element enthält. Mit diesen beiden Membern bestimmen Sie, pro Artikel, den Typ und Wert der Informationen zu den Unterelementen, die angezeigt wird, wenn das Strukturelement-Steuerelement in der Berichtsansicht ist. Weitere Informationen finden Sie unter [CListCtrl:: SetItem](../mfc/reference/clistctrl-class.md#setitem).

Zusätzliche Member geben Sie Text, Symbol, Status und die Daten des Elements. "Elementdaten" ein Anwendung definierter Wert, der ein Listenansichtselement zugeordnet ist. Weitere Informationen zu den `LV_ITEM` Struktur, siehe [CListCtrl:: GetItem](../mfc/reference/clistctrl-class.md#getitem).

Andere Versionen von `InsertItem` nehmen Sie eine oder mehrere unterschiedliche Werte, die für Elemente in der `LV_ITEM` Struktur, sodass Sie nur die Member initialisiert werden, Sie unterstützen möchten. Im Allgemeinen das Strukturelement-Steuerelement verwaltet die Speicherung für Listenelemente, aber Sie können einige der Informationen in Ihrer Anwendung speichern stattdessen mit "Rückrufelemente." Weitere Informationen finden Sie unter [Rückrufelemente und Rückrufmaske](../mfc/callback-items-and-the-callback-mask.md) in diesem Thema und [Rückrufelemente und Rückrufmaske](/windows/desktop/Controls/using-list-view-controls) im Windows SDK.

Weitere Informationen finden Sie unter [hinzufügen Listenansicht-Elementen und Unterelementen](/windows/desktop/Controls/using-list-view-controls).

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
