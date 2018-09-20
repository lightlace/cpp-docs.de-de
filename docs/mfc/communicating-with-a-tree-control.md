---
title: Kommunikation mit dem Struktursteuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78bb6a6d6421a5336f8efbffc7d24a6121e208e6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432151"
---
# <a name="communicating-with-a-tree-control"></a>Kommunizieren mit dem Struktursteuerelement

Sie verwenden verschiedene Methoden zum Aufrufen von Memberfunktionen einer [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Objekt je nachdem, wie das Objekt erstellt wurde:

- Ist das Strukturansicht-Steuerelement in einem Dialogfeld, verwenden Sie eine Membervariable des Typs `CTreeCtrl` , die Sie erstellen, in die Dialogfeldklasse.

- Wenn die Strukturansicht-Steuerelement ein untergeordnetes Fenster ist, verwenden Sie die `CTreeCtrl` Objekt (oder Zeiger), verwendet Sie zum Erstellen des Objekts.

- Bei Verwendung einer `CTreeView` Objekt, verwenden Sie die Funktion [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) zum Abrufen eines Verweises auf das Strukturansicht-Steuerelement. Sie können eines anderen Verweises mit diesem Wert zu initialisieren oder Zuweisen der Adresse des Verweises auf eine `CTreeCtrl` Zeiger.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

