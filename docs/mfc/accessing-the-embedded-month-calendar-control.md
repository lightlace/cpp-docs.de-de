---
title: "Zugreifen auf das eingebettete Monatskalender-Steuerelement"
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
  - "CDateTimeCtrl-Klasse, Zugreifen auf eingebettete Steuerelemente"
  - "CMonthCalCtrl-Klasse, Ändern der Schriftart"
  - "DateTimePicker-Steuerelement [MFC]"
  - "DateTimePicker-Steuerelement [MFC], Zugriff auf den Monatskalender"
  - "Monatskalender-Steuerelement, Ändern der Schriftart"
  - "Monatskalender-Steuerelement, eingebettet in der Datum/Uhrzeit-Auswahl"
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zugreifen auf das eingebettete Monatskalender-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Auf das eingebettete Monatskalender\-Steuerelement\-Objekt kann vom `CDateTimeCtrl`\-Objekt durch einen Aufruf der Memberfunktion [GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md) zugegriffen werden.  
  
> [!NOTE]
>  Die eingebettete Monatskalender\-Steuerelement wird nur verwendet, wenn das Steuerelement für die Datums\- und Zeitauswahl nicht den festgelegten **DTS\_UPDOWN**  Format hat.  
  
 Dies ist hilfreich, wenn Sie bestimmten Attributen ändern möchten, bevor das eingebettete Steuerelement angezeigt wird.  Um dies zu erreichen, bearbeiten Sie die **DTN\_DROPDOWN** Benachrichtigung, abzurufen das Monatskalender\-Steuerelement \(mit [CDateTimeCtrl::GetMonthCalCtrl](../Topic/CDateTimeCtrl::GetMonthCalCtrl.md)\) und nehmen Sie die Änderungen.  Leider ist das Monatskalender\-Steuerelement nicht erhalten.  
  
 Das heißt, die Benutzeranforderungen, wenn die Anzeige des Monatskalender\-Steuerelements, ein neues Monatskalender\-Steuerelement erstellt wird \(vor der **DTN\_DROPDOWN** Benachrichtigung\).  Das Steuerelement zerstört wird \(nach der **DTN\_CLOSEUP** Benachrichtigung\) wenn es vom Benutzer schließen wird.  Dies bedeutet, dass alle Attribute, die, Sie, bevor das eingebettete Steuerelement angezeigt wird, gehen verloren ändern, wenn das eingebettete Steuerelement geschlossen wird.  
  
 Im folgenden Beispiel wird dieses Verfahren, mithilfe eines Handlers für die **DTN\_DROPDOWN** Benachrichtigung.  Die Codeänderungen die Hintergrundfarbe des Monatskalender\-Steuerelements, mit einem Aufruf von [SetMonthCalColor](../Topic/CDateTimeCtrl::SetMonthCalColor.md), z Grau.  Der Code ist, wie folgt:  
  
 [!CODE [NVC_MFCControlLadenDialog#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#5)]  
  
 Wie bereits erwähnt, sind alle Änderungen an den Eigenschaften des Monatskalender\-Steuerelements, mit zwei Ausnahmen verloren, wenn das eingebettete Steuerelement geschlossen wird.  Die erste Ausnahme, die Farben des Monatskalender\-Steuerelements, ist bereits erläutert wird.  Die zweite Ausnahme ist die Schriftart, die vom Monatskalender\-Steuerelement verwendet wird.  Sie können die Standardschriftart ändern, indem Sie einen Aufruf von [CDateTimeCtrl::SetMonthCalFont](../Topic/CDateTimeCtrl::SetMonthCalFont.md) ausführen und das Handle einer vorhandenen Schriftart übergeben.  Das folgenden Beispiel \(wobei `m_dtPicker` das Datum und Zeitsteuerobjekt ist\), wird eine andere Methode:  
  
 [!CODE [NVC_MFCControlLadenDialog#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#6)]  
  
 Sobald die Schriftart, mit einem Aufruf von `CDateTimeCtrl::SetMonthCalFont`, die neue Schriftart wird gespeichert und verwendet geändert wurde beim nächsten Mal, wenn ein Monatskalender angezeigt werden soll.  
  
## Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)