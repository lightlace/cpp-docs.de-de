---
title: "Hinzuf&#252;gen von Elementen zum Headersteuerelement"
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
  - "CHeaderCtrl-Klasse, Hinzufügen von Elementen"
  - "Steuerelemente [MFC], Header"
  - "Headersteuerelemente, Hinzufügen von Elementen zu"
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen von Elementen zum Headersteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie das Header\-Steuerelement \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\) im übergeordneten Fenster erstellt haben, fügen Sie in "Kopfzeilenelemente" hinzu Sie benötigen: normalerweise pro Spalte ein.  
  
### So ein Headerelement hinzufügen  
  
1.  Bereiten Sie eine Struktur vor [HD\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247).  
  
2.  Aufruf [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md), Struktur übergeben.  
  
3.  Wiederholen Sie Schritte 1 und 2 für zusätzliche Elemente.  
  
 Weitere Informationen finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Hinzufügen eines Elements zu einem Header\-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)