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
ms.openlocfilehash: f84e36a2a002610c294653012c40707fddcaba54
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607466"
---
# <a name="destroying-the-dialog-box"></a>Zerstören des Dialogfelds

Modale Dialogfelder werden normalerweise auf den Stapelrahmen erstellt und zerstört, wenn die Beendigung der Funktion, die sie erstellt wurden. Des Destruktors des Dialogfeldobjekts wird immer dann aufgerufen, wenn das Objekt den Gültigkeitsbereich verlässt.

Nicht modale Dialogfelder werden normalerweise erstellt und im Besitz von einem übergeordneten Ansicht oder der Zielframe, Fenster – Hauptrahmenfenster der Anwendung oder einem Dokumentrahmenfenster. Der Standardwert [OnClose](../mfc/reference/cwnd-class.md#onclose) handleraufrufen [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), die zerstört das Fenster "im Dialogfeld". Wenn das Dialogfeld allein, keine Zeiger oder andere spezielle Besitzsemantik steht, sollten Sie überschreiben [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) das C++-Dialog-Objekt zu zerstören. Sie sollten auch überschreiben, [OnCancel](../mfc/reference/cdialog-class.md#oncancel) , und rufen Sie `DestroyWindow` aus darin. Wenn dies nicht der Fall ist, wird der Besitzer des Dialogfelds sollte die C++-Objekt zu zerstören, wenn es nicht mehr erforderlich ist.

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

