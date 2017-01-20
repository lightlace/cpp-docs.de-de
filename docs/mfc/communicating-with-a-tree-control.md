---
title: "Kommunizieren mit dem Struktursteuerelement"
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
  - "Kommunikationen, Struktursteuerelemente"
  - "CTreeCtrl-Klasse, Rückrufmemberfunktionen"
  - "Struktursteuerelemente"
  - "Struktursteuerelemente, Kommunikation mit"
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Kommunizieren mit dem Struktursteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie verwenden unterschiedliche Methoden zum Aufrufen von Memberfunktionen in einem [CTreeCtrl](../mfc/reference/ctreectrl-class.md)\-Objekt abhängig davon, wie das Objekt erstellt wurde:  
  
-   Wenn dem Tree\-Steuerelement in einem Dialogfeld ist, verwenden Sie eine Membervariable vom Typ `CTreeCtrl`, die Sie in der Dialogfeldklasse erstellen.  
  
-   Wenn dem Tree\-Steuerelement ein untergeordnetes Fenster ist, verwenden Sie das `CTreeCtrl`\-Objekt \(oder Zeiger\), das Sie verwendet haben, um das Objekt zu erstellen.  
  
-   Wenn Sie ein `CTreeView`\-Objekt verwenden, verwenden Sie die [CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md), um einen Verweis auf das Struktursteuerelement abzurufen.  Sie können einen anderen Verweis mit diesem Wert initialisiert oder Adresse des Verweises in `CTreeCtrl` einem Zeiger zuweisen.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)