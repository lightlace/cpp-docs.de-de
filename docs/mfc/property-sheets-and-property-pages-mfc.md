---
title: "Eigenschaftenbl&#228;tter und Eigenschaftenseiten (MFC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertyPage-Klasse, Eigenschaftenblätter und -Seiten"
  - "CPropertySheet-Klasse, Eigenschaftenblätter und -Seiten"
  - "MFC-Dialogfelder, Registerkarten"
  - "Eigenschaftenseiten, Eigenschaftenblätter"
  - "Eigenschaftenblätter, Eigenschaftenseiten"
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Eigenschaftenbl&#228;tter und Eigenschaftenseiten (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine MFC\- [Dialogfeld](../mfc/dialog-boxes.md) kann auf "Registerkartendialogfeld" Blick nehmen, indem Eigenschaftenblätter und Eigenschaftenseiten integriert.  Wird ein "Eigenschaftenblatt" in MFC, diese Art von Dialogfeld auf, ähnlich vielen Dialogfeldern in Microsoft Word, Excel, und Visual C\+\+, wird, einen Stapel Blätter im Registerkartenformat, ähnlich wie ein Stapel Dateiordner, die vom Vordergrund, die sehen zurückzuziehen, oder eine Gruppe überlappende Fenster zu enthalten.  Steuerelemente auf die Vorder\- Registerkarte angezeigt; nur die Registerkarte mit Bezeichnung ist auf den von Registerkarten angezeigt.  Eigenschaftenblätter sind für die Verwaltung für zahlreiche Eigenschaften oder Einstellungen besonders nützlich, die relativ ordentlich in einige Gruppen ab.  Normalerweise kann ein Eigenschaftenblatt eine Benutzeroberfläche vereinfachen, indem einige eigene Dialogfelder ersetzt.  
  
 Seit MFC 4.0, werden Eigenschaftenblätter und Eigenschaftenseiten mit der allgemeinen Steuerelemente implementiert, die Windows 95 und Windows NT 3,51 und höher werden.  
  
 Eigenschaftenblätter werden mit Klassen [CPropertySheet](../mfc/reference/cpropertysheet-class.md) und [CPropertyPage](../mfc/reference/cpropertypage-class.md) implementiert \(beschrieben in der *MFC\-Referenz*\).  `CPropertySheet` definiert das Gesamtdialogfeld, das mehrere "Seiten" auf `CPropertyPage` enthalten kann.  
  
 Informationen zum Erstellen und Verwenden von Eigenschaftenblättern, finden Sie im Thema [Eigenschaftenblätter](../mfc/property-sheets-mfc.md).  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Eigenschaftenblätter und Eigenschaftenseiten in MFC](../mfc/property-sheets-and-property-pages-in-mfc.md)   
 [Datenaustausch](../mfc/exchanging-data.md)   
 [Erstellen eines nicht modalen Eigenschaftenblatts](../mfc/creating-a-modeless-property-sheet.md)   
 [Verwenden der Schaltfläche „Anwenden“](../mfc/handling-the-apply-button.md)