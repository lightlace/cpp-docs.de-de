---
title: Erstellen von modalen Dialogfeldern | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a8bc947dbaf9cecc680f3cdbd8e6b429d2bcd5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342428"
---
# <a name="creating-modal-dialog-boxes"></a>Erstellen von modalen Dialogfeldern
Um ein modales Dialogfeld zu erstellen, rufen Sie entweder die beiden öffentlichen Konstruktoren deklariert [CDialog](../mfc/reference/cdialog-class.md). Rufen Sie als Nächstes des Dialogfeldobjekts [DoModal](../mfc/reference/cdialog-class.md#domodal) Memberfunktion, um das Dialogfeld anzuzeigen und Interaktion mit der Anwendung zu verwalten, bis der Benutzer OK oder "Abbrechen". Diese Verwaltung durch `DoModal` ist, was die modales Dialogfeld. Für modale Dialogfelder `DoModal` lädt die Dialogressource.  
  
## <a name="see-also"></a>Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)

