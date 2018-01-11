---
title: "Schließen des Dialogfelds | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4c311a8d09ac3e1329b495fc321028e9f674993
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="closing-the-dialog-box"></a>Schließen des Dialogfelds
Ein modales Dialogfeld wird geschlossen, wenn der Benutzer eine der zugehörigen Schaltflächen, in der Regel auf die Schaltfläche "OK" oder die Schaltfläche "Abbrechen wählt". Dann die Schaltfläche OK oder auf "Abbrechen" bewirkt, dass Windows auf das Dialogfeldobjekt senden eine **BN_CLICKED** Steuerelement-Benachrichtigung mit der Schaltfläche-ID, entweder des **IDOK** oder **IDCANCEL**. `CDialog`Stellt Handlerfunktionen für diese Nachrichten: `OnOK` und `OnCancel`. Die Handler rufen die `EndDialog` Memberfunktion, um das Dialogfeld zu schließen. Sie können auch aufrufen `EndDialog` aus Ihrem eigenen Code. Weitere Informationen finden Sie unter der ["EndDialog"](../mfc/reference/cdialog-class.md#enddialog) Memberfunktion der Klasse `CDialog` in der *MFC-Referenz*.  
  
 Anordnen von schließen und löschen ein nicht modales Dialogfeld überschreiben `PostNcDestroy` und Aufrufen der **löschen** Operator auf die **dies** Zeiger. [Zerstören des Dialogfelds](../mfc/destroying-the-dialog-box.md) wird erläutert, was daraufhin geschieht.  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

