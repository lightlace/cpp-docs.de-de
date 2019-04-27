---
title: Kommunizieren mit dem Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: 920608724ebb362b91efdcb3eab50b80acd20474
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151254"
---
# <a name="communicating-with-a-tree-control"></a>Kommunizieren mit dem Struktursteuerelement

Sie verwenden verschiedene Methoden zum Aufrufen von Memberfunktionen einer [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Objekt je nachdem, wie das Objekt erstellt wurde:

- Ist das Strukturansicht-Steuerelement in einem Dialogfeld, verwenden Sie eine Membervariable des Typs `CTreeCtrl` , die Sie erstellen, in die Dialogfeldklasse.

- Wenn die Strukturansicht-Steuerelement ein untergeordnetes Fenster ist, verwenden Sie die `CTreeCtrl` Objekt (oder Zeiger), verwendet Sie zum Erstellen des Objekts.

- Bei Verwendung einer `CTreeView` Objekt, verwenden Sie die Funktion [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) zum Abrufen eines Verweises auf das Strukturansicht-Steuerelement. Sie können eines anderen Verweises mit diesem Wert zu initialisieren oder Zuweisen der Adresse des Verweises auf eine `CTreeCtrl` Zeiger.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
