---
title: Zerstören des Dialogfelds | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 863b70f3bf4e9828d69024b838dce43abbba26be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425911"
---
# <a name="destroying-the-dialog-box"></a>Zerstören des Dialogfelds

Modale Dialogfelder werden normalerweise auf den Stapelrahmen erstellt und zerstört, wenn die Beendigung der Funktion, die sie erstellt wurden. Des Destruktors des Dialogfeldobjekts wird immer dann aufgerufen, wenn das Objekt den Gültigkeitsbereich verlässt.

Nicht modale Dialogfelder werden normalerweise erstellt und im Besitz von einem übergeordneten Ansicht oder der Zielframe, Fenster – Hauptrahmenfenster der Anwendung oder einem Dokumentrahmenfenster. Der Standardwert [OnClose](../mfc/reference/cwnd-class.md#onclose) handleraufrufen [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), die zerstört das Fenster "im Dialogfeld". Wenn das Dialogfeld allein, keine Zeiger oder andere spezielle Besitzsemantik steht, sollten Sie überschreiben [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) das C++-Dialog-Objekt zu zerstören. Sie sollten auch überschreiben, [OnCancel](../mfc/reference/cdialog-class.md#oncancel) , und rufen Sie `DestroyWindow` aus darin. Wenn dies nicht der Fall ist, wird der Besitzer des Dialogfelds sollte die C++-Objekt zu zerstören, wenn es nicht mehr erforderlich ist.

## <a name="see-also"></a>Siehe auch

[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

