---
title: "Verarbeiten von Benachrichtigungsmeldungen in Steuerelementen f&#252;r Zeit und Datum | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DTN_CLOSEUP"
  - "DTN_DATETIMECHANGE"
  - "DTN_DROPDOWN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl-Klasse, Handlingbenachrichtigungen"
  - "DateTimePicker-Steuerelement [MFC]"
  - "DateTimePicker-Steuerelement [MFC], Handlingbenachrichtigungen"
  - "DTN_CLOSEUP-Benachrichtigung"
  - "DTN_DATETIMECHANGE-Benachrichtigung"
  - "DTN_DROPDOWN-Benachrichtigung"
  - "DTN_FORMAT-Benachrichtigung"
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verarbeiten von Benachrichtigungsmeldungen in Steuerelementen f&#252;r Zeit und Datum
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Während Benutzer mit dem Steuerelement für die Datums\- und Zeitauswahl interagieren, sendet das Steuerelement \(`CDateTimeCtrl`\) Benachrichtigungen übergeordneten Fenster, gewöhnlich eine Ansicht oder ein Dialogfeldobjekt.  Bearbeiten Sie diese Meldungen, wenn Sie etwas in der Antwort ausführen möchten.  Wenn der Benutzer beispielsweise die Datums\- Zeitauswahl wird, um das eingebettete Monatskalender\-Steuerelement anzuzeigen, ist die **DTN\_DROPDOWN** Benachrichtigung gesendet.  
  
 Verwenden Sie das Eigenschaftenfenster, um Benachrichtigungshandlern der übergeordneten Klasse für diese Meldungen hinzuzufügen, die Sie implementieren möchten.  
  
 Die folgende Liste beschreibt die verschiedenen Benachrichtigungen, die vom Steuerelement für die Datums\- und Zeitauswahl gesendet werden.  
  
-   **DTN\_DROPDOWN** benachrichtigt das übergeordnete Element, dass das eingebettete Monatskalender\-Steuerelement im Begriff ist angezeigt werden.  Diese Benachrichtigung wird nur gesendet, wenn das **DTS\_UPDOWN** Stil nicht festgelegt wurde.  Weitere Informationen über diese Benachrichtigung, finden Sie unter [Zugreifen auf das eingebettete Monatskalender\-Steuerelement](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   **DTN\_CLOSEUP** benachrichtigt das übergeordnete Element, dass das eingebettete Monatskalender\-Steuerelement im Begriff ist geschlossen werden.  Diese Benachrichtigung wird nur gesendet, wenn das **DTS\_UPDOWN** Stil nicht festgelegt wurde.  
  
-   **DTN\_DATETIMECHANGE** benachrichtigt das übergeordnete Element, dass eine Änderung im Steuerelement vorgenommen ist.  
  
-   **DTN\_FORMAT** benachrichtigt das übergeordnete Element, dass Text benötigt wird, auf einem Rückrufgebiet angezeigt werden.  Weitere Informationen über diese und Rückruffelder Benachrichtigungs\-, finden Sie unter [Verwenden der Rückruf\-Felder in einem Steuerelement für die Datums\- und Zeitauswahl](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN\_FORMATQUERY** aufgerufen, um das übergeordnete Element die maximal zulässige Größe der Zeichenfolge zu stellen, die auf einem Rückrufgebiet angezeigt wird.  Beim Behandeln dieser Benachrichtigung können ordnungsgemäß der Anzeige das Steuerelement jederzeit, die ausgegeben wird und reduziert Flimmern in der Anzeige des Steuerelements.  Weitere Informationen über diese Benachrichtigung, finden Sie unter [Verwenden der Rückruf\-Felder in einem Steuerelement für die Datums\- und Zeitauswahl](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN\_USERSTRING** benachrichtigt das übergeordnete Element, dass der Benutzer beendet, den Inhalt des Steuerelements für die Datums\- und Zeitauswahl zu bearbeiten.  Diese Benachrichtigung wird nur gesendet, wenn das **DTS\_APPCANPARSE** Format festgelegt wurde.  
  
-   **DTN\_WMKEYDOWN** benachrichtigt das übergeordnete wenn Benutzer auf einem Rückrufgebiet.  Bearbeiten Sie diese Benachrichtigung, dieselbe Tastaturantwort zu emulieren, die für NichtRückruffelder in einem Steuerelement für die Datums\- und Zeitauswahl unterstützt wird.  Weitere Informationen über diese Benachrichtigung, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Unterstützung von Rückruf\-Feldern in einem DTP\-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb761726).  
  
## Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)