---
title: Anordnen von Elementen im Headersteuerelement
ms.date: 11/04/2016
f1_keywords:
- DS_DRAGDROP
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
ms.openlocfilehash: bae351d921c25993d6b7029f9052e1938179673b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392649"
---
# <a name="ordering-items-in-the-header-control"></a>Anordnen von Elementen im Headersteuerelement

Nachdem Sie haben [einem Kopfzeilen-Steuerelement Elemente hinzugefügt](../mfc/adding-items-to-the-header-control.md), können Sie bearbeiten oder Abrufen von Informationen zu deren Reihenfolge mit den folgenden Funktionen:

- [CHeaderCtrl:: GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) und [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)

   Ruft ab, und die links-nach-rechts-Reihenfolge der Headerelemente festgelegt.

- [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).

   Ruft den Indexwert für ein bestimmtes Headerelement ab.

Zusätzlich zu den vorherigen Memberfunktionen kann die HDS_DRAGDROP-Stil den Benutzer Drag & drop-Header-Elemente, in dem Kopfzeilen-Steuerelement. Weitere Informationen finden Sie unter [Bereitstellen von Drag & Drop-Unterstützung für Headerelemente](../mfc/providing-drag-and-drop-support-for-header-items.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)
