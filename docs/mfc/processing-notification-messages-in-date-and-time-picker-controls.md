---
title: Verarbeiten von Nachrichten in Datums- und Zeitauswahl Steuerelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 630792eb4bdd89cbe8081894c4ee026437568f3b
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930763"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Steuerelementen für Zeit und Datum
Benutzer interagieren mit das Datum und Uhrzeit Kontoauswahl-Steuerelement, das Steuerelement (`CDateTimeCtrl`) sendet benachrichtigungsmeldungen an das übergeordnete Fenster, normalerweise ein Ansichts- oder Dialogfeldobjekt-Objekt. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Wenn der Benutzer die Datums- / Zeitauswahl anzuzeigenden das eingebettete Monatskalender-Steuerelement geöffnet wird, wird z. B. die DTN_DROPDOWN-Benachrichtigung gesendet.  
  
 Verwenden Sie das Eigenschaftenfenster, um der übergeordneten Klasse Benachrichtigungshandler für die Nachrichten hinzuzufügen, die Sie implementieren möchten.  
  
 Die folgende Liste beschreibt die verschiedenen Benachrichtigungen gesendet werden, durch die Datums- / Zeitauswahl-Steuerelement.  
  
-   DTN_DROPDOWN benachrichtigt, ist das übergeordnete Element, das das eingebettete Monatskalender-Steuerelement angezeigt wird. Diese Benachrichtigung wird nur gesendet, wenn der DTS_UPDOWN-Stil nicht festgelegt wurde. Weitere Informationen über diese Benachrichtigung finden Sie unter [den Zugriff auf das eingebettete Monatskalender-Steuerelement](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   DTN_CLOSEUP benachrichtigt, ist das übergeordnete Element, das das eingebettete Monatskalender-Steuerelement geschlossen werden. Diese Benachrichtigung wird nur gesendet, wenn der DTS_UPDOWN-Stil nicht festgelegt wurde.  
  
-   DTN_DATETIMECHANGE Benachrichtigt das übergeordnete Element, das im Steuerelement eine Änderung aufgetreten ist.  
  
-   DTN_FORMAT benachrichtigt, benötigt das übergeordnete Element, das Text in einem Rückruffeld angezeigt werden. Weitere Informationen über diese Benachrichtigung und Rückruffeldern finden Sie unter [Verwenden von Rückruffeldern in einem Datum und Uhrzeit die Datumsauswahl](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   DTN_FORMATQUERY Fordert das übergeordnete Element, um die maximal zulässige Größe der Zeichenfolge anzugeben, die in einem Rückruffeld angezeigt wird. Behandeln diese Benachrichtigung kann das Steuerelement ordnungsgemäß Anzeigeausgabe jederzeit aktiv, vermindern des Flimmerns innerhalb des Steuerelements anzeigen. Weitere Informationen über diese Benachrichtigung finden Sie unter [Verwenden von Rückruffeldern in einem Datum und Uhrzeit die Datumsauswahl](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   Das übergeordnete Element den Abschluss der Benutzer den Inhalt von den Datums- / Zeitauswahl bearbeiten DTN_USERSTRING Benachrichtigt gesteuert werden. Diese Benachrichtigung wird nur gesendet, wenn das DTS_APPCANPARSE-Format festgelegt wurde.  
  
-   DTN_WMKEYDOWN benachrichtigt das übergeordnete Element aus, wenn der Benutzer in einem Rückruffeld eingibt. Behandeln Sie diese Benachrichtigung zum Emulieren der gleichen Tastatur-Antwort für nicht-Rückruffeldern in einem Datums- und Zeitauswahl-Steuerelement unterstützt. Weitere Informationen über diese Benachrichtigung finden Sie unter [Unterstützung von Rückruffeldern in einem Steuerelement DTP](http://msdn.microsoft.com/library/windows/desktop/bb761726) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

