---
title: "Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen | Microsoft Docs"
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
  - "CListCtrl-Klasse, Verarbeitungsmeldungen"
  - "Verarbeitungsmeldungen"
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie Benutzer auf Spaltenüberschriften klicken, ziehen Sie Symbole, Bearbeitungsbezeichnungen usw. das Listensteuerelement \([Verwendung](../mfc/reference/clistctrl-class.md)\) sendet Benachrichtigungen übergeordneten Fenster.  Bearbeiten Sie diese Meldungen, wenn Sie etwas in der Antwort ausführen möchten.  Wenn Benutzer auf einen Spaltenheader klickt, sollten Sie die Elemente basierend auf dem Inhalt der per Spalte, wie in Microsoft Outlook sortieren.  
  
 Prozess\- **WM\_NOTIFY** Meldungen im Listensteuerelement in der Ansicht oder in Dialogklasse.  Verwenden Sie das Eigenschaftenfenster, um eine [OnChildNotify](../Topic/CWnd::OnChildNotify.md)\-Handlerfunktion mit einer switch\-Anweisung zu erstellen, auf dem die Benachrichtigung behandelt wird.  
  
 Eine Liste der Benachrichtigungen, die ein Listensteuerelement an das übergeordnete Fenster gesendet werden kann, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Listenansicht\-Steuerelement\-Verweis](http://msdn.microsoft.com/library/windows/desktop/bb774737).  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)