---
title: "Drehfeld-Schaltfl&#228;chenstile"
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
  - "CSpinButtonCtrl-Klasse, Stile"
  - "Drehfeld-Steuerelement, Stile"
  - "Stile, CSpinButtonCtrl"
  - "Stile, Drehfeld-Steuerelement"
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Drehfeld-Schaltfl&#228;chenstile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Viele der Einstellungen für ein Drehfeld \([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)\) werden durch Stile gesteuert.  Sie können die folgenden Stile mithilfe des Fensters **Eigenschaften** im Dialog\-Editor festlegen.  
  
-   **Ausrichtung** Entweder vertikal oder horizontal.  Steuert die Ausrichtung der Pfeilschaltflächen.  Zugeordnet mit dem Format `UDS_HORZ`.  
  
-   **Ausrichtung** eine von unabhängigem, von links oder rechts.  Steuert den Speicherort des Drehfelds.  NACH\-LINKS\-TASTE und rechte Position das Drehfeld neben dem Buddyfenster.  Die Breite des Buddyfensters wird verringert, um das Drehfeld anzupassen.  Zugeordnet mit den `UDS_ALIGNLEFT` und `UDS_ALIGNRIGHT` Stile.  
  
-   **Auto Buddy** wählt automatisch das vorherige Fenster in Z\-Reihenfolge der als Buddyfenster dem Drehfeld aus.  In einer Dialogvorlage ist dies das Steuerelement, das dem Drehfeld in der Aktivierreihenfolge unmittelbar vorangestellt ist.  Zugeordnet mit dem Format `UDS_AUTOBUDDY`.  
  
-   **Set Buddy Integer** bewirkt das Drehfeld\-Steuerelement, die Beschriftung des Buddyfensters zu inkrementieren und dekrementieren zu, während die aktuelle Position ändert.  Zugeordnet mit dem Format `UDS_SETBUDDYINT`.  
  
-   **Keine Tausende** wird nicht das Tausendertrennzeichen im Wert in der Beschriftung des Buddyfensters ein.  Zugeordnet mit dem Format `UDS_NOTHOUSANDS`.  
  
    > [!NOTE]
    >  Legen Sie dieses Format festgelegt, wenn Sie ermöglichen \(DDX\) verwenden möchten um den ganzzahligen Wert vom Buddysteuerelement abzurufen.  `DDX_Text` akzeptiert nicht eingebettete Tausendertrennzeichen.  
  
-   **Umbruch** bewirkt die Position "umbrochen" als Wert über den Bereich des Steuerelements hinausgeht erhöht oder verringert wird.  Zugeordnet mit dem Format `UDS_WRAP`.  
  
-   **Pfeiltasten** bewirkt das Drehfeld, Position zu erhöhen oder zu vermindern, wenn die NACH\-OBEN\- und NACH\-UNTEN\-TASTEN gedrückt werden.  Zugeordnet mit dem Format `UDS_ARROWKEYS`.  
  
## Siehe auch  
 [Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)