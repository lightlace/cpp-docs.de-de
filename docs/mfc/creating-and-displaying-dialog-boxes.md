---
title: Erstellen und Anzeigen von Dialogfeldern | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d436301a979dbba2bc4a922f8427f355a398f654
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

