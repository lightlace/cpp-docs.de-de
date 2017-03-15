---
title: "Verarbeiten von Benachrichtigungen des Headersteuerelements | Microsoft Docs"
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
  - "CHeaderCtrl-Klasse, Verarbeitungsmeldungen"
  - "Steuerelemente [MFC], Header"
  - "Header-Steuerelementebenachrichtigungen"
  - "Headersteuerelemente, Verarbeitungsmeldungen"
  - "Benachrichtigungen, Verarbeiten für CHeaderCtrl"
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verarbeiten von Benachrichtigungen des Headersteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der Ansicht oder in Dialogklasse verwenden Sie das Eigenschaftenfenster, um eine [OnChildNotify](../Topic/CWnd::OnChildNotify.md)\-Handlerfunktion mit einer switch\-Anweisung für alle Benachrichtigungsmeldungen des Header\-Steuerelements \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\) zu erstellen, die Sie bearbeiten möchten \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  Benachrichtigungen werden dem übergeordneten Fenster, wenn der Benutzer auf ein Headerelement klickt oder doppelklicken, zieht einen Unterteiler zwischen Elementen, z. B. gesendet.  
  
 Die Benachrichtigungsmeldungen, die einem Header\-Steuerelement zugeordnet werden, werden in [Header\-Steuerelement\-Verweis](http://msdn.microsoft.com/library/windows/desktop/bb775239) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] aufgeführt.  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)