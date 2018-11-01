---
title: Listenelemente und Bildlisten
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: cae387dc028df46a7891e68d49f5f0c5a89126c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571040"
---
# <a name="list-items-and-image-lists"></a>Listenelemente und Bildlisten

Eine "Item" in einem Listensteuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) besteht aus ein Symbol, eine Bezeichnung, und möglicherweise anderen Informationen (in "Unterelemente").

Die Symbole für Listenelemente-Steuerelement sind in Bildlisten enthalten. Eine Bildliste enthält Symbole in voller Größe in der Symbolansicht verwendet wird. Eine zweite, optionale Bildliste enthält kleinere Versionen der gleichen Symbole für die Verwendung in anderen Ansichten des Steuerelements. Eine dritte optionale Liste enthält die "State"-Bilder, z. B. Kontrollkästchen für die Anzeige vor der kleinen Symbole in bestimmten Ansichten. Eine vierte optionale Liste enthält Images, die in den einzelnen Header-Elemente des Steuerelements angezeigt werden.

> [!NOTE]
>  Wenn ein Listenansicht-Steuerelement mit dem Stil LVS_SHAREIMAGELISTS erstellt wird, sind Sie verantwortlich für das Löschen der Bildliste, wenn sie nicht mehr verwendet werden. Geben Sie, dass dieses Format, wenn Sie das gleiche Image zuweisen, mehrere Listenansicht-Steuerelemente enthält; Andernfalls könnten mehr als ein Steuerelement versuchen, dieselbe Bildliste zerstört.

Weitere Informationen Listenelemente, finden Sie unter [List View Image Lists](/windows/desktop/Controls/using-list-view-controls) und [Elementen und Unterelementen](/windows/desktop/Controls/using-list-view-controls) im Windows SDK. Siehe auch die Klasse [CImageList](../mfc/reference/cimagelist-class.md) in die *MFC-Referenz* und [Verwenden von CImageList](../mfc/using-cimagelist.md) in dieser Artikelreihe.

Um ein Listensteuerelement erstellen zu können, müssen Sie angeben Bildlisten verwendet werden, wenn Sie neue Elemente in der Liste einfügen. Das folgende Beispiel veranschaulicht dieses Verfahren, in denen *gezeigt* ist ein Zeiger des Typs `CImageList` und *M_listctrl* ist eine `CListCtrl` -Datenmember.

[!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]

Wenn Sie planen nicht, um Symbole in der Listenansicht oder Steuerelement anzuzeigen, erforderlich nicht jedoch Bildlisten.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

