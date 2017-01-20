---
title: "Hinzuf&#252;gen von Registerkarten zum Registersteuerelement"
ms.custom: na
ms.date: "12/14/2016"
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
  - "CTabCtrl-Klasse, Hinzufügen von Registerkarten"
  - "Setzen von Registerkarten bei CTabCtrls"
  - "Registerkarten-Steuerelemente, Hinzufügen von Registerkarten"
  - "Registerkarten, Hinzufügen zur CTabCtrl-Klasse"
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen von Registerkarten zum Registersteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie das Registersteuerelement \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) erstellt haben, fügen Sie auf Registerkarten hinzu, Sie benötigen.  
  
### So ein Registerkartenelement hinzufügen  
  
1.  Bereiten Sie eine Struktur vor [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554).  
  
2.  Aufruf [CTabCtrl::InsertItem](../Topic/CTabCtrl::InsertItem.md), Struktur übergeben.  
  
3.  Wiederholen Sie Schritte 1 und 2 für weitere Registerkartenelemente.  
  
 Weitere Informationen finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Erstellen eines Registersteuerelements](http://msdn.microsoft.com/library/windows/desktop/bb760550).  
  
## Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)