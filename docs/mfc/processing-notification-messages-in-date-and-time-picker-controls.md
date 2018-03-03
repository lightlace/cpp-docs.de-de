---
title: Verarbeiten von Nachrichten in Datums- und Zeitauswahl Steuerelemente | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
dev_langs:
- C++
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 836714f7a7ca17d759d0d71a7cbb30d63fdfaf95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Steuerelementen für Zeit und Datum
Benutzer interagieren mit das Datum und Uhrzeit Kontoauswahl-Steuerelement, das Steuerelement (`CDateTimeCtrl`) sendet benachrichtigungsmeldungen an das übergeordnete Fenster, normalerweise ein Ansichts- oder Dialogfeldobjekt-Objekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Beispielsweise, wenn der Benutzer öffnet die Datums- / Zeitauswahl anzuzeigenden das eingebettete Monatskalender-Steuerelement, das **DTN_DROPDOWN** Benachrichtigung wird gesendet.  
  
 Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.  
  
 Die folgende Liste beschreibt die verschiedenen Benachrichtigungen gesendet werden, durch die Datums- / Zeitauswahl-Steuerelement.  
  
-   **DTN_DROPDOWN** benachrichtigt das übergeordnete Element, die das eingebettete Monatskalender-Steuerelement angezeigt werden. Diese Benachrichtigung wird nur gesendet, wenn die **DTS_UPDOWN** Stil nicht festgelegt wurde. Weitere Informationen über diese Benachrichtigung finden Sie unter [den Zugriff auf das eingebettete Monatskalender-Steuerelement](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   **DTN_CLOSEUP** benachrichtigt das übergeordnete Element, die das eingebettete Monatskalender-Steuerelement geschlossen werden. Diese Benachrichtigung wird nur gesendet, wenn die **DTS_UPDOWN** Stil nicht festgelegt wurde.  
  
-   **DTN_DATETIMECHANGE** benachrichtigt das übergeordnete Element, das im Steuerelement eine Änderung aufgetreten ist.  
  
-   **DTN_FORMAT** benachrichtigt dem übergeordnete Element Text erforderlich ist, um in einem Rückruffeld angezeigt werden. Weitere Informationen über diese Benachrichtigung und Rückruffeldern finden Sie unter [Verwenden von Rückruffeldern in einem Datum und Uhrzeit die Datumsauswahl](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN_FORMATQUERY** fordert das übergeordnete Element, um die maximal zulässige Größe der Zeichenfolge anzugeben, die in einem Rückruffeld angezeigt wird. Behandeln diese Benachrichtigung kann das Steuerelement ordnungsgemäß Anzeigeausgabe jederzeit aktiv, vermindern des Flimmerns innerhalb des Steuerelements anzeigen. Weitere Informationen über diese Benachrichtigung finden Sie unter [Verwenden von Rückruffeldern in einem Datum und Uhrzeit die Datumsauswahl](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN_USERSTRING** benachrichtigt dem übergeordnete Element, dass der Benutzer den Inhalt von Datums- / Zeitauswahl-Steuerelement bearbeiten abgeschlossen wurde. Diese Benachrichtigung wird nur gesendet, wenn die **DTS_APPCANPARSE** Stil festgelegt wurde.  
  
-   **DTN_WMKEYDOWN** benachrichtigt Sie das übergeordnete Element aus, wenn ein Rückruffeld der Benutzer eingibt. Behandeln Sie diese Benachrichtigung zum Emulieren der gleichen Tastatur-Antwort für nicht-Rückruffeldern in einem Datums- und Zeitauswahl-Steuerelement unterstützt. Weitere Informationen über diese Benachrichtigung finden Sie unter [Unterstützung von Rückruffeldern in einem Steuerelement DTP](http://msdn.microsoft.com/library/windows/desktop/bb761726) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

