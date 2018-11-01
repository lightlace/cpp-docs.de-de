---
title: Zerstören des Listensteuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: 85089919ccb81003dad1eab439fa8a0d127fd9ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568345"
---
# <a name="destroying-the-list-control"></a>Zerstören des Listensteuerelements

Wenn Sie einbetten Ihrer [CListCtrl](../mfc/reference/clistctrl-class.md) als Datenmember einer Klasse Ansichts- oder Dialogfeldobjekt Objekt zerstört wird, wenn der Besitzer zerstört wird. Bei Verwendung einer [CListView](../mfc/reference/clistview-class.md), das Framework zerstört das Steuerelement beim Zerstören der Ansicht.

Wenn Sie für Ihre Liste-Daten in die Anwendung statt auf das Strukturelement-Steuerelement zu speichernde anordnen möchten, müssen Sie für deren Freigabe gesorgt. Weitere Informationen finden Sie unter [Rückrufelemente und Rückrufmaske](/windows/desktop/Controls/using-list-view-controls) im Windows SDK.

Darüber hinaus sind Sie verantwortlich für das Aufheben der Zuordnung Bildlisten, die Sie erstellt und mit dem Listensteuerelement-Objekt verknüpft.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

