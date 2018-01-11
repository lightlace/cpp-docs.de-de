---
title: Zugreifen auf das eingebettete Monatskalender-Steuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e37d23a7d5d860d55e18f709c873a40d8f24f1c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="accessing-the-embedded-month-calendar-control"></a>Zugreifen auf das eingebettete Monatskalender-Steuerelement
Das eingebettete Monatskalender-Kalender-Steuerelementobjekt möglich, die von der `CDateTimeCtrl` Objekt durch einen Aufruf der [Memberfunktion GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) Memberfunktion.  
  
> [!NOTE]
>  Das eingebettete Monatskalender-Steuerelement wird nur verwendet, wenn die Datums- / Zeitauswahl-Steuerelement keinen der **DTS_UPDOWN** Satz formatieren.  
  
 Dies ist nützlich, wenn Sie möchten bestimmte Attribute zu ändern, bevor das eingebettete Steuerelement angezeigt wird. Um dies zu erreichen, behandeln die **DTN_DROPDOWN** Benachrichtigung im Monatskalender-Steuerelement abgerufen (mit [CDateTimeCtrl:: GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)), und nehmen Sie Ihre Änderungen vor. Leider ist im Monatskalender-Steuerelement nicht persistent.  
  
 Das heißt, wenn der Benutzer die Anzeige der im Monatskalender-Steuerelement anfordert, ein neues Monatskalender-Steuerelement erstellt (vor der **DTN_DROPDOWN** Benachrichtigung). Zerstört das Steuerelement (nach der **DTN_CLOSEUP** Benachrichtigung), als vom Benutzer verworfen. Dies bedeutet, dass alle Attribute, die Sie ändern, bevor das eingebettete Steuerelement angezeigt wird, die verloren gegangen sind, wenn das eingebettete Steuerelement geschlossen wird.  
  
 Das folgende Beispiel veranschaulicht dieses Verfahren, mit einem Handler für das **DTN_DROPDOWN** Benachrichtigung. Der Code ändert die Hintergrundfarbe der im Monatskalender-Steuerelement, mit einem Aufruf von [SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor), grau dargestellt. Der Code sieht folgendermaßen aus:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 Wie bereits erwähnt, sind alle Änderungen an Eigenschaften der im Monatskalender-Steuerelement verloren geht, mit zwei Ausnahmen, wenn das eingebettete Steuerelement geschlossen wird. Die erste Ausnahme, die Farben der im Monatskalender-Steuerelement, wurde bereits besprochen. Zweitens ist die Schriftart für den Monatskalender-Steuerelement. Sie können die Schriftart ändern, indem einem Aufruf an [CDateTimeCtrl:: SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), übergeben das Handle für eine vorhandene Schriftart. Im folgenden Beispiel (, in denen `m_dtPicker` ist das Steuerelementobjekt Datum und Uhrzeit) veranschaulicht eine mögliche Methode:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 Nachdem die Schriftart, mit einem Aufruf von geändert wurde `CDateTimeCtrl::SetMonthCalFont`, die neue Schriftart gespeichert und verwendet das nächste Mal ein Monatskalender angezeigt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

