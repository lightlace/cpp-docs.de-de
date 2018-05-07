---
title: Nicht modale Dialogfelder erstellen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2055312c7418b14c9b274649db8faa297554257e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creating-modeless-dialog-boxes"></a>Erstellen von nicht modalen Dialogfeldern
Für ein nicht modales Dialogfeld müssen Sie Ihren eigenen öffentlichen Konstruktor in eigener Dialogfeldklassen bereitstellen. Um ein nicht modales Dialogfeld erstellen, die public-Konstruktor aufrufen und dann des Dialogfeldobjekts [erstellen](../mfc/reference/cdialog-class.md#create) Memberfunktion versucht, die Ressource zu laden. Sie können Aufrufen **erstellen** während oder nach dem Konstruktoraufruf. Wenn die Ressource die Eigenschaft hat **WS_VISIBLE**, das Dialogfeld wird sofort angezeigt. Wenn nicht, die Sie aufrufen müssen dessen [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

