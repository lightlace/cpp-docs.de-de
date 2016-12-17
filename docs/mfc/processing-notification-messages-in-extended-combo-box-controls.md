---
title: "Verarbeiten von Benachrichtigungsmeldungen in erweiterten Kombinationsfeld-Steuerelementen"
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
  - "Erweiterte Kombinationsfelder, Benachrichtigungen"
  - "Benachrichtigungen, erweiterte Kombinationsfeld-Steuerelemente"
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verarbeiten von Benachrichtigungsmeldungen in erweiterten Kombinationsfeld-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Benutzer mit dem erweiterten Kombinationsfeld interagieren, sendet das Steuerelement \(`CComboBoxEx`\) Benachrichtigungen an sein übergeordnetes Fenster, normalerweise ein Ansichts\- oder Dialogfeldobjekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer z. B. die Dropdownliste aktiviert oder in das Editierfeld des Steuerelements klickt, wird die Benachrichtigung **CBEN\_BEGINEDIT** gesendet.  
  
 Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.  
  
 In der folgenden Liste sind die verschiedenen Benachrichtigungen beschrieben, die vom erweiterten Kombinationsfeld\-Steuerelement gesendet werden.  
  
-   **CBEN\_BEGINEDIT** Wird gesendet, wenn der Benutzer die Dropdownliste aktiviert oder in das Editierfeld des Steuerelements klickt.  
  
-   **CBEN\_DELETEITEM** Wird gesendet, wenn ein Element gelöscht wurde.  
  
-   **CBEN\_DRAGBEGIN** Wird gesendet, wenn der Benutzer beginnt, das Bild des angezeigten Elements auf den Editierteil des Steuerelements zu ziehen.  
  
-   **CBEN\_ENDEDIT** Wird gesendet, wenn der Benutzer einen Vorgang im Editierfeld abgeschlossen oder ein Element in der Dropdownliste des Steuerelements ausgewählt hat.  
  
-   **CBEN\_GETDISPINFO** Wird gesendet, um Anzeigeinformationen zu einem Rückrufelement abzurufen.  
  
-   **CBEN\_INSERTITEM** Wird gesendet, wenn ein neues Element in das Steuerelement eingefügt wurde.  
  
## Siehe auch  
 [Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Steuerelemente](../mfc/controls-mfc.md)