---
title: Eigenschaftenblätter und Eigenschaftenseiten (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 882b2d93ba7938017f64b1ad8fb8e680e0af42db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348988"
---
# <a name="property-sheets-and-property-pages-mfc"></a>Eigenschaftenblätter und Eigenschaftenseiten (MFC)
Eine MFC [Dialogfeld](../mfc/dialog-boxes.md) für einen Blick "Registerkarte Dialogfeld" ausführen können, die durch das Integrieren von Eigenschaftenblätter und Eigenschaftenseiten. "Eigenschaftenblatt" in MFC aufgerufen, wird diese Art von Dialogfeldern, ähnlich wie bei vielen Dialogfeldern in Microsoft Word, Excel und Visual C++ enthält einen Stapel von im Registerkartenformat Blättern, ähnlich wie ein Stapel Dateiordner von vorne nach hinten oder eine Gruppe von kaskadierenden Windows angezeigt. Die Steuerelemente auf der Registerkarte "front" sind sichtbar. nur der Registerkarte "mit der Bezeichnung" wird auf der rückseitigen Registerkarten angezeigt. Eigenschaftenblätter sind besonders nützlich für das Verwalten einer großen Anzahl von Eigenschaften oder Einstellungen, die relativ sauber in verschiedene Gruppen liegen. In der Regel kann ein Eigenschaftenblatt eine Benutzeroberfläche vereinfachen, indem Sie mehrere separate Dialogfelder ersetzen.  
  
 Ab MFC 4.0 werden Eigenschaftenblätter und Eigenschaftenseiten implementiert die Standardsteuerelemente, die die im Lieferumfang von Windows 95 und Windows NT, Version 3.51 und höher verwenden.  
  
 Eigenschaftenblätter werden mit den Klassen implementiert [CPropertySheet](../mfc/reference/cpropertysheet-class.md) und [CPropertyPage](../mfc/reference/cpropertypage-class.md) (beschrieben der *MFC-Referenz*). `CPropertySheet` definiert das Dialogfeld insgesamt, die mehrere "Seiten" auf der Grundlage enthalten können `CPropertyPage`.  
  
 Informationen zum Erstellen und Arbeiten mit Eigenschaftenblätter, finden Sie im Thema [Eigenschaftenblätter](../mfc/property-sheets-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Eigenschaftenblätter und Eigenschaftenseiten in MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [Austauschen von Daten](../mfc/exchanging-data.md)   
 [Erstellen eines nicht modalen Eigenschaftenblatts](../mfc/creating-a-modeless-property-sheet.md)   
 [Verwenden der Schaltfläche „Anwenden“](../mfc/handling-the-apply-button.md)

