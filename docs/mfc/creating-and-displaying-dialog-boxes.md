---
title: Erstellen und Anzeigen von Dialogfeldern | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fcac345a572f8b33d76692d6852e2dc28698367
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creating-and-displaying-dialog-boxes"></a>Erstellen und Anzeigen von Dialogfeldern
Erstellen eines Dialogfeldobjekts ist ein zwei-Phasen-Vorgang. Zunächst erstellen Sie das Dialogfeldobjekt, und erstellen Sie im Dialogfenster. Modale und nicht modale Dialogfelder unterscheiden sich in einem gewissen im Prozess zum Erstellen und anzeigen. Die folgende Tabelle enthält wie modale und nicht modale Dialogfeld normalerweise erstellt und angezeigt werden.  
  
### <a name="dialog-creation"></a>Dialogfeld-Erstellung  
  
|Dialogfeldtyp|Zum Erstellen|  
|-----------------|----------------------|  
|[Ohne Modus](../mfc/creating-modeless-dialog-boxes.md)|Erstellen Sie `CDialog`, rufen Sie anschließend **erstellen** Memberfunktion.|  
|[Modale](../mfc/creating-modal-dialog-boxes.md)|Erstellen Sie `CDialog`, rufen Sie anschließend `DoModal` Memberfunktion.|  
  
 Wenn Sie möchten, können das Dialogfeld aus einer [in-Memory-Dialogfeldvorlage](../mfc/using-a-dialog-template-in-memory.md) , den Sie erstellt haben anstatt von einer Dialogfeldvorlagen-Ressource. Dies ist jedoch ein-Thema für fortgeschrittene.  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

