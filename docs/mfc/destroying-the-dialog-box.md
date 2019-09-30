---
title: Zerstören des Dialogfelds
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
ms.openlocfilehash: 8b407c6e832dde7a5865146e7cc12d1840d3234a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685849"
---
# <a name="destroying-the-dialog-box"></a>Zerstören des Dialogfelds

Modale Dialogfelder werden normalerweise auf dem Stapel Rahmen erstellt und zerstört, wenn die Funktion, die Sie erstellt hat, endet. Der Dekonstruktor des Dialog Objekts wird aufgerufen, wenn das Objekt den Gültigkeitsbereich verlässt.

Dialogfelder ohne Modus werden normalerweise erstellt und im Besitz einer übergeordneten Ansicht oder eines Rahmen Fensters, – das Hauptrahmen Fenster der Anwendung oder ein Dokument Rahmen Fenster. Der standardmäßige [OnClose](../mfc/reference/cwnd-class.md#onclose) -Handler ruft [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)auf, wodurch das Dialogfeld Fenster zerstört wird. Wenn das Dialogfeld allein und ohne Zeiger darauf oder eine andere besondere Besitz Semantik steht, sollten Sie [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) außer Kraft setzen, um C++ das Dialog Objekt zu zerstören. Sie sollten auch [OnCancel](../mfc/reference/cdialog-class.md#oncancel) überschreiben und `DestroyWindow` darin abrufen. Wenn dies nicht der Fall ist, sollte der Besitzer des Dialog C++ Felds das Objekt zerstören, wenn es nicht mehr benötigt wird.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)
