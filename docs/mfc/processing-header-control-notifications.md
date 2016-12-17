---
title: "Verarbeiten von Benachrichtigungen des Headersteuerelements"
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
  - "CHeaderCtrl-Klasse, Verarbeitungsmeldungen"
  - "Steuerelemente [MFC], Header"
  - "Header-Steuerelementebenachrichtigungen"
  - "Headersteuerelemente, Verarbeitungsmeldungen"
  - "Benachrichtigungen, Verarbeiten für CHeaderCtrl"
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verarbeiten von Benachrichtigungen des Headersteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der Ansicht oder in Dialogklasse verwenden Sie das Eigenschaftenfenster, um eine [OnChildNotify](../Topic/CWnd::OnChildNotify.md)\-Handlerfunktion mit einer switch\-Anweisung für alle Benachrichtigungsmeldungen des Header\-Steuerelements \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\) zu erstellen, die Sie bearbeiten möchten \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  Benachrichtigungen werden dem übergeordneten Fenster, wenn der Benutzer auf ein Headerelement klickt oder doppelklicken, zieht einen Unterteiler zwischen Elementen, z. B. gesendet.  
  
 Die Benachrichtigungsmeldungen, die einem Header\-Steuerelement zugeordnet werden, werden in [Header\-Steuerelement\-Verweis](http://msdn.microsoft.com/library/windows/desktop/bb775239) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] aufgeführt.  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)