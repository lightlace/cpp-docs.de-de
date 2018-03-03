---
title: Verarbeiten von Benachrichtigungsmeldungen in erweiterten Kombinationsfeld-Steuerelementen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a78e7b9fd8f9c67f14a4bb51088866785d372cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in erweiterten Kombinationsfeld-Steuerelementen
Wenn Benutzer mit dem erweiterten Kombinationsfeld interagieren, sendet das Steuerelement (`CComboBoxEx`) Benachrichtigungen an sein übergeordnetes Fenster, normalerweise ein Ansichts- oder Dialogfeldobjekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer z. B. die Dropdownliste aktiviert oder in das Editierfeld des Steuerelements klickt, wird die Benachrichtigung **CBEN_BEGINEDIT** gesendet.  
  
 Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.  
  
 In der folgenden Liste sind die verschiedenen Benachrichtigungen beschrieben, die vom erweiterten Kombinationsfeld-Steuerelement gesendet werden.  
  
-   **CBEN_BEGINEDIT** Wird gesendet, wenn der Benutzer die Dropdownliste aktiviert oder in das Editierfeld des Steuerelements klickt.  
  
-   **CBEN_DELETEITEM** Wird gesendet, wenn ein Element gelöscht wurde.  
  
-   **CBEN_DRAGBEGIN** Wird gesendet, wenn der Benutzer beginnt, das Bild des angezeigten Elements auf den Editierteil des Steuerelements zu ziehen.  
  
-   **CBEN_ENDEDIT** Wird gesendet, wenn der Benutzer einen Vorgang im Editierfeld abgeschlossen oder ein Element in der Dropdownliste des Steuerelements ausgewählt hat.  
  
-   **CBEN_GETDISPINFO** Wird gesendet, um Anzeigeinformationen zu einem Rückrufelement abzurufen.  
  
-   **CBEN_INSERTITEM** Wird gesendet, wenn ein neues Element in das Steuerelement eingefügt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

