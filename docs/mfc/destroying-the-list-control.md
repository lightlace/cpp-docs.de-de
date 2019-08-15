---
title: Zerstören des Listensteuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: 5004026da6bb309cc2c966384724b7b98e254e1d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508697"
---
# <a name="destroying-the-list-control"></a>Zerstören des Listensteuerelements

Wenn Sie das [CListCtrl](../mfc/reference/clistctrl-class.md) -Objekt als Datenmember einer Sicht oder Dialogfeld Klasse einbetten, wird es zerstört, wenn der Besitzer zerstört wird. Wenn Sie eine [CListView](../mfc/reference/clistview-class.md)verwenden, zerstört das Framework das Steuerelement, wenn es die Ansicht zerstört.

Wenn Sie festlegen, dass einige der Listen Daten in der Anwendung und nicht im Listen Steuerelement gespeichert werden sollen, müssen Sie die Aufhebung der Zuordnung anordnen. Weitere Informationen finden Sie unter [Rückruf Elemente und Rückruf Maske](/windows/win32/Controls/using-list-view-controls) in der Windows SDK.

Außerdem sind Sie verantwortlich für das Aufheben der Zuordnung von Image Listen, die Sie erstellt und mit dem Listen Steuerelement-Objekt verknüpft haben.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
