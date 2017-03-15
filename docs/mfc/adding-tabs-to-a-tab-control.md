---
title: "Hinzuf&#252;gen von Registerkarten zum Registersteuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
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