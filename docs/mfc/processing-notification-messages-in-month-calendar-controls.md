---
title: Verarbeiten von Benachrichtigungsmeldungen in Monatskalender-Steuerelementen | Microsoft Docs
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
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75b07973b1410c7f8bbaa527876efa9b9f1481a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Monatskalender-Steuerelementen
Als Benutzer mit der im Monatskalender-Steuerelement (Auswahl von Datumsangaben und/oder einen anderen Monat anzeigen), das Steuerelement interagieren (`CMonthCalCtrl`) sendet benachrichtigungsmeldungen an das übergeordnete Fenster, normalerweise ein Ansichts- oder Dialogfeldobjekt-Objekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer einen neuen Monat anzeigen auswählt, können Sie z. B. einen Satz mit Datumsangaben bereitstellen, die hervorgehoben werden sollen.  
  
 Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.  
  
 Die folgende Liste beschreibt die verschiedenen Benachrichtigungen per im Monatskalender-Steuerelement.  
  
-   **MCN_GETDAYSTATE** fordert Informationen darüber, welche Tage in Fettschrift angezeigt werden soll. Informationen zur Behandlung dieser benachrichtigungs finden Sie unter [Einstellen des Tagesstatus für ein Monatskalender-Steuerelement](../mfc/setting-the-day-state-of-a-month-calendar-control.md).  
  
-   **MCN_SELCHANGE** benachrichtigt das übergeordnete Element, das das ausgewählte Datum oder der Datumsbereich geändert wurde.  
  
-   **MCN_SELECT** benachrichtigt das übergeordnete Element, das eine explizite Datumsauswahl festgelegt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

