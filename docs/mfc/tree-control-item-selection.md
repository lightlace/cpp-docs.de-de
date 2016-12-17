---
title: "Wechseln der Auswahl in einem Struktursteuerelement"
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
  - "Steuerelemente [MFC], Auswählen von Elementen in"
  - "CTreeCtrl-Klasse, Elementauswahl"
  - "Elementauswahl in einem Struktursteuerelement"
  - "Struktursteuerelemente, Elementauswahl"
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Wechseln der Auswahl in einem Struktursteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn die Auswahl von einem Element zum anderen ändert, sendet eine Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) [TVN\_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) und [TVN\_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) Benachrichtigungsmeldungen.  Beide Benachrichtigungen schließen einen Wert, der angibt, ob die Änderungen das Ergebnis eines Mausklicks oder einer Tastatureingabe ist.  Die Benachrichtigungen schließen auch Informationen über das Element, das die Auswahl und das Element abrufen, das die Auswahl verliert.  Sie können diese Informationen verwenden, um festzulegen Elementattribute, die vom Auswahlzustand des Elements abhängig sind.  Die Rückgabe von **TRUE** auf **TVN\_SELCHANGING** verhindert die Auswahl des Ändern; Rückgabe von **FALSE** ermöglicht die Änderung.  
  
 Eine Anwendung kann die Auswahl ändern, indem sie die [SelectItem](../Topic/CTreeCtrl::SelectItem.md)\-Memberfunktion aufruft.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)