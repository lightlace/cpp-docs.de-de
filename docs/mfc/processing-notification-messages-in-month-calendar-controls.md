---
title: "Verarbeiten von Benachrichtigungsmeldungen in Monatskalender-Steuerelementen | Microsoft Docs"
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
  - "CMonthCalCtrl-Klasse, Tageszustände"
  - "CMonthCalCtrl-Klasse, Benachrichtigungen"
  - "Monatskalender-Steuerelement, Benachrichtigungsmeldungen"
  - "Benachrichtigungen, für CMonthCalCtrl"
  - "Benachrichtigungen, Monatskalender-Steuerelement"
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Verarbeiten von Benachrichtigungsmeldungen in Monatskalender-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Während Benutzer mit dem Monatskalender\-Steuerelement \(Datumsangaben auswählen und\/oder einen anderen Monat wird\) interagieren, sendet das Steuerelement \(`CMonthCalCtrl`\) Benachrichtigungen übergeordneten Fenster, gewöhnlich eine Ansicht oder ein Dialogfeldobjekt.  Bearbeiten Sie diese Meldungen, wenn Sie etwas in der Antwort ausführen möchten.  Wenn der Benutzer zu einem neuen Monat auswählt, um anzuzeigen, können Sie einen Satz von Datumsangaben bereitstellen, die hervorgehoben werden sollen.  
  
 Verwenden Sie das Eigenschaftenfenster, um Benachrichtigungshandlern der übergeordneten Klasse für diese Meldungen hinzuzufügen, die Sie implementieren möchten.  
  
 Die folgende Liste beschreibt die verschiedenen Benachrichtigungen, die vom Monatskalender\-Steuerelement gesendet werden.  
  
-   **MCN\_GETDAYSTATE** erfordert Informationen, über die Tage fett formatiert werden sollen.  Informationen über das Behandeln dieser Benachrichtigung, finden Sie unter [Festlegen des Tags\-Zustandes eines Monatskalender\-Steuerelements](../mfc/setting-the-day-state-of-a-month-calendar-control.md).  
  
-   **MCN\_SELCHANGE** benachrichtigt das übergeordnete Element, dass das ausgewählte Datum oder der Gültigkeitsbereich des Datums geändert hat.  
  
-   **MCN\_SELECT** benachrichtigt das übergeordnete Element, dass eine explizite Datumsauswahl gemacht wurde.  
  
## Siehe auch  
 [Verwenden von CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)