---
title: "Eigenschaftenbl&#228;tter und Eigenschaftenseiten in MFC"
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
  - "Steuerelemente [MFC], Eigenschaftenblätter"
  - "Eigenschaftenseiten, MFC"
  - "Eigenschaftenblätter, MFC"
  - "Registerkarten-Dialogfelder"
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Eigenschaftenbl&#228;tter und Eigenschaftenseiten in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eigenschaftenblatts, auch ein Dialogfeld im Registerformat, ist ein Dialogfeld, das Eigenschaftenseiten enthält.  Jede Eigenschaftenseite ist auf einer Dialogfeldvorlagen\-Ressource und enthält Steuerelemente.  Sie ist auf einer Seite mit einer Registerkarte im Vordergrund eingeschlossen.  Die Registerkarte wird die Seite und gibt sein Zweck an.  Benutzer klicken auf eine Registerkarte im Eigenschaftenblatt, um mehrere Steuerelemente auszuwählen.  
  
 Verwendungsseiten, um die Steuerelemente im Eigenschaftenblatt in übersichtlicher Sätze zu gruppieren.  Das enthaltende Eigenschaftenblatt hat in der Regel mehrere Steuerelemente von eigenen.  Diese betreffen alle Seiten.  
  
 Eigenschaftenblätter basieren auf Klasse [CPropertySheet](../mfc/reference/cpropertysheet-class.md).  Eigenschaftenseiten basieren auf Klasse [CPropertyPage](../mfc/reference/cpropertypage-class.md).  
  
 Eigenschaftenblatts ist eine besondere Art von Dialogfeld, das im Allgemeinen verwendet wird, um die Attribute einiger externen Objekts zu ändern, wie die aktuelle Auswahl in einer Ansicht.  Das Eigenschaftenblatt enthält drei Hauptkomponenten: das enthaltende Dialogfeld, mindestens Eigenschaftenseiten einzeln angezeigt und eine Registerkarte oben auf jeder Seite, die der Benutzer klickt, um die Seite auszuwählen.  Eigenschaftenblätter sind für Situationen, in denen Sie einige ähnliche Einstellungssätze oder Optionen haben zu ändern.  Eigenschaftenblatts gruppiert Informationen in einer leicht verständliche Weise.  
  
> [!NOTE]
>  Wenn Sie versuchen, ein Eigenschaftenblatt anzuzeigen, indem Sie `CPropertySheet::DoModal` verwenden, kann das System generierte eine Ausnahme der ersten Chance.  Diese Ausnahme tritt auf, da das System versucht, [Fensterstile](../mfc/reference/window-styles.md) des Objekts zu ändern, bevor das Objekt erstellt wurde.  Weitere Informationen über diese Ausnahme sowie, wie sie dies vermeiden können oder sie, finden Sie unter [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md).  
  
## Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)