---
title: Zerstören des Dialogfelds | Microsoft Docs
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
ms.openlocfilehash: 66a3ef9a72107ffb36a75834a6e197aba394c420
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343923"
---
# <a name="destroying-the-dialog-box"></a>Zerstören des Dialogfelds
Modale Dialogfelder werden normalerweise auf den Stapelrahmen erstellt und zerstört, wenn die Funktion, die sie erstellt wurden. Das Dialogfeldobjekt-Destruktor wird aufgerufen, wenn das Objekt den Gültigkeitsbereich verlässt.  
  
 Nicht modale Dialogfelder werden normalerweise erstellt und im Besitz eines übergeordneten Ansicht oder den Frame-Fensters – Hauptrahmenfenster für die Anwendung oder einem Dokumentrahmenfenster. Die Standardeinstellung [OnClose](../mfc/reference/cwnd-class.md#onclose) Ereignishandler ruft [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow), dadurch wird das Dialogfeld-Fenster zerstört. Wenn das Dialogfeld allein, keine Zeiger oder andere spezielle Besitzsemantik steht, sollten Sie überschreiben [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) , die C++-Dialog-Objekt zu zerstören. Sie sollten auch überschreiben [OnCancel](../mfc/reference/cdialog-class.md#oncancel) , und rufen Sie `DestroyWindow` aus einstuft. Wenn dies nicht der Fall ist, wird der Besitzer des Dialogfelds sollte die C++-Objekt zerstört, wenn es nicht mehr erforderlich ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

