---
title: "Verarbeiten von Benachrichtigungsmeldungen in einem Grundleisten-Steuerelement | Microsoft Docs"
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
  - "CReBarCtrl-Klasse, Gesendete Benachrichtigungsmeldungen von"
  - "Benachrichtigungen, CReBarCtrl"
  - "RBN_-Benachrichtigungsmeldungen"
  - "RBN_-Benachrichtigungsmeldungen, Beschreibung von"
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verarbeiten von Benachrichtigungsmeldungen in einem Grundleisten-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der übergeordneten Klasse des Infoleiste\-Steuerelements, erstellen Sie eine Handlerfunktion `OnChildNotify` mit einer switch\-Anweisung für alle Benachrichtigungsmeldungen des Infoleiste\-Steuerelements \(`CReBarCtrl`\), die Sie bearbeiten möchten.  Benachrichtigungen werden auf das übergeordnete Fenster gesendet, wenn der Benutzer über Objekte dem Grundleistensteuerelement, ändert das Layout der Infoleistenbänder, löscht Bänder vom Grundleistensteuerelement, usw. zieht.  
  
 Die folgenden Benachrichtigungsmeldungen können vom Infoleiste\-Steuerelement\-Objekt gesendet werden:  
  
-   **RBN\_AUTOSIZE** gesendet durch ein Infoleistensteuerelement \(erstellt mit dem **RBS\_AUTOSIZE** Format\) Wenn die Infoleiste automatisch angepasst wird.  
  
-   **RBN\_BEGINDRAG** gesendet durch eine Infoleiste, wenn der Benutzer beginnt, ein Band ziehen.  
  
-   **RBN\_CHILDSIZE** gesendet durch eine Infoleiste, wenn das untergeordnete Fenster eines Bands Größe geändert wird.  
  
-   **RBN\_DELETEDBAND** gesendet durch eine Infoleiste, nachdem ein Band gelöscht wurde.  
  
-   **RBN\_DELETINGBAND** gesendet durch eine Infoleiste, wenn ein Band im Begriff ist gelöscht.  
  
-   **RBN\_ENDDRAG** gesendet durch eine Infoleiste, wenn der Benutzer beendet, ein Band zu ziehen.  
  
-   **RBN\_GETOBJECT** gesendet durch ein Infoleistensteuerelement \(erstellt mit dem **RBS\_REGISTERDROP** Format\) Wenn ein Objekt über ein Band im Steuerelement gezogen wird.  
  
-   **RBN\_HEIGHTCHANGE** gesendet durch eine Infoleiste, wenn die Höhe geändert hat.  
  
-   **RBN\_LAYOUTCHANGED** gesendet durch eine Infoleiste, wenn der Benutzer das Layout der Bänder des Steuerelements ändert.  
  
 Weitere Informationen über diese Benachrichtigungen, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Infoleiste\-Steuerelement\-Verweis](http://msdn.microsoft.com/library/windows/desktop/bb774375).  
  
## Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)