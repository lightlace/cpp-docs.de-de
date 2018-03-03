---
title: Erstellen von modalen Dialogfeldern | Microsoft Docs
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
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 815db891514eb03169dac2ad29e50469d74dcfee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-modal-dialog-boxes"></a>Erstellen von modalen Dialogfeldern
Um ein modales Dialogfeld zu erstellen, rufen Sie entweder die beiden öffentlichen Konstruktoren deklariert [CDialog](../mfc/reference/cdialog-class.md). Rufen Sie als Nächstes des Dialogfeldobjekts [DoModal](../mfc/reference/cdialog-class.md#domodal) Memberfunktion, um das Dialogfeld anzuzeigen und Interaktion mit der Anwendung zu verwalten, bis der Benutzer OK oder "Abbrechen". Diese Verwaltung durch `DoModal` ist, was die modales Dialogfeld. Für modale Dialogfelder `DoModal` lädt die Dialogressource.  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

