---
title: Kommunizieren mit dem Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: a5749b76468a7ba30cd48dc3a9b61f2de7ac67b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654183"
---
# <a name="communicating-with-a-tree-control"></a>Kommunizieren mit dem Struktursteuerelement

Sie verwenden verschiedene Methoden zum Aufrufen von Memberfunktionen einer [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Objekt je nachdem, wie das Objekt erstellt wurde:

- Ist das Strukturansicht-Steuerelement in einem Dialogfeld, verwenden Sie eine Membervariable des Typs `CTreeCtrl` , die Sie erstellen, in die Dialogfeldklasse.

- Wenn die Strukturansicht-Steuerelement ein untergeordnetes Fenster ist, verwenden Sie die `CTreeCtrl` Objekt (oder Zeiger), verwendet Sie zum Erstellen des Objekts.

- Bei Verwendung einer `CTreeView` Objekt, verwenden Sie die Funktion [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) zum Abrufen eines Verweises auf das Strukturansicht-Steuerelement. Sie können eines anderen Verweises mit diesem Wert zu initialisieren oder Zuweisen der Adresse des Verweises auf eine `CTreeCtrl` Zeiger.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

