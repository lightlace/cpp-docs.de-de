---
title: "Verarbeiten von Benachrichtigungsmeldungen des Registersteuerelements | Microsoft Docs"
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
  - "CTabCtrl-Klasse, Verarbeitungsmeldungen"
  - "Benachrichtigungen, Verarbeiten in CTabCtrl"
  - "Benachrichtigungen, Registerkarten-Steuerelemente"
  - "Verarbeitungsmeldungen"
  - "Registerkarten-Steuerelemente, Verarbeitungsmeldungen"
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verarbeiten von Benachrichtigungsmeldungen des Registersteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Da Benutzer Registerkarten oder auf Schaltflächen klicken, sendet das Registersteuerelement \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) Benachrichtigungen übergeordneten Fenster.  Bearbeiten Sie diese Meldungen, wenn Sie etwas in der Antwort ausführen möchten.  Wenn Benutzer auf eine Registerkarte klicken, sollten Sie Steuerelementdaten auf der Seite vor dem Anzeigen sie vorab festlegen.  
  
 Prozess\- **WM\_NOTIFY** Meldungen im Registersteuerelement in der Ansicht oder in Dialogklasse.  Verwenden Sie das Eigenschaftenfenster, um eine [OnChildNotify](../Topic/CWnd::OnChildNotify.md)\-Handlerfunktion mit einer switch\-Anweisung zu erstellen, auf dem die Benachrichtigung behandelt wird.  Eine Liste der Benachrichtigungen, die ein Tab\-Steuerelement an das übergeordnete Fenster gesendet werden kann, finden Sie im Abschnitt **Benachrichtigungen** von [Tab\-Steuerelement\-Verweis](http://msdn.microsoft.com/library/windows/desktop/bb760548) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)