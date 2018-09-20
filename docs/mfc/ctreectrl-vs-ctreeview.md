---
title: CTreeCtrl im Vergleich zu CTreeView | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs:
- C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8acaecbdfb99b8ae0b27023145a0ef6aee1f219
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399148"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl im Vergleich zu CTreeView

MFC stellt zwei Klassen, die die Struktur-Steuerelemente kapseln: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) und [CTreeView](../mfc/reference/ctreeview-class.md). Jede Klasse ist in verschiedenen Situationen nützlich.

Verwendung `CTreeCtrl` Wenn Sie ein einfaches untergeordnetes Fenstersteuerelement benötigen z. B. in einem Dialogfeld. Insbesondere empfiehlt verwenden `CTreeCtrl` bei anderen untergeordneten Steuerelemente im Fenster an, wie ein normales Dialogfeld.

Verwendung `CTreeView` Wenn Sie möchten das Strukturansicht-Steuerelement, das wie ein Fenster anzeigen, in die Dokument-/Ansichtarchitektur fungiert sowohl als auch ein Strukturansicht-Steuerelement. Ein `CTreeView` nimmt den gesamten Clientbereich eines Rahmenfensters oder Teilungsfenster. Es wird automatisch angepasst, wenn das übergeordnete Fenster angepasst wird, und Command-Meldungen von Menüs, Zugriffstasten und Symbolleisten verarbeitet werden können. Da ein Strukturansicht-Steuerelement zum Anzeigen der Struktur erforderlichen Daten enthält, das entsprechende Document-Objekt muss nicht kompliziert sein – Sie können sogar [CDocument](../mfc/reference/cdocument-class.md) als Dokumenttyp in Ihrer Dokumentvorlage.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

