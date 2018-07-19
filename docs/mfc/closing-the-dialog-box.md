---
title: Schließen des Dialogfelds | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c800c204fd09057585064397d459f92c9ded272d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341744"
---
# <a name="closing-the-dialog-box"></a>Schließen des Dialogfelds
Ein modales Dialogfeld wird geschlossen, wenn der Benutzer eine der zugehörigen Schaltflächen, in der Regel auf die Schaltfläche "OK" oder die Schaltfläche "Abbrechen wählt". Dann die Schaltfläche OK oder auf "Abbrechen" bewirkt, dass Windows auf das Dialogfeldobjekt senden eine **BN_CLICKED** Steuerelement-Benachrichtigung mit der Schaltfläche-ID, entweder des **IDOK** oder **IDCANCEL**. `CDialog` Stellt Handlerfunktionen für diese Nachrichten: `OnOK` und `OnCancel`. Die Handler rufen die `EndDialog` Memberfunktion, um das Dialogfeld zu schließen. Sie können auch aufrufen `EndDialog` aus Ihrem eigenen Code. Weitere Informationen finden Sie unter der ["EndDialog"](../mfc/reference/cdialog-class.md#enddialog) Memberfunktion der Klasse `CDialog` in der *MFC-Referenz*.  
  
 Anordnen von schließen und löschen ein nicht modales Dialogfeld überschreiben `PostNcDestroy` und Aufrufen der **löschen** Operator auf die **dies** Zeiger. [Zerstören des Dialogfelds](../mfc/destroying-the-dialog-box.md) wird erläutert, was daraufhin geschieht.  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

