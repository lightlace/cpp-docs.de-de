---
title: "Arbeiten mit dem Registersteuerelement | Microsoft Docs"
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
  - "CTabCtrl-Klasse, Verwenden"
  - "Registerkarten-Steuerelemente, Verwenden"
  - "Registerkarten-Steuerelemente, Arbeiten mit"
ms.assetid: 819488e3-4944-44b7-9483-195edb8e0aed
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Arbeiten mit dem Registersteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die einfachste Methode, ein Tab\-Steuerelement \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) zu verwenden ist, indem es einer Dialogfeldvorlagen\-Ressource mit dem Dialog\-Editor hinzufügt.  Sie können ein Tab\-Steuerelement auch allein verwenden.  MFC ruft **InitCommonControls** für Sie auf.  Die Hauptaufgaben sind, wie folgt:  
  
-   [Erstellen des Registersteuerelements](../mfc/creating-the-tab-control.md)  
  
-   [Hinzufügen von Tabstopps in einem Registersteuerelement](../mfc/adding-tabs-to-a-tab-control.md)  
  
-   [Verarbeiten von Tab\-Steuerelement\-Benachrichtigungsmeldungen](../mfc/processing-tab-control-notification-messages.md)  
  
 Wenn das Tab\-Steuerelement\-Objekt in einer übergeordneten Ansicht oder einer Dialogfeldklasse eingebettet wird, wird das Steuerelement zerstört, wenn das übergeordnete Element zerstört wird.  
  
## Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)