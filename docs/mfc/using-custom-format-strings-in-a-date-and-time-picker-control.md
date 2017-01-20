---
title: "Verwenden von benutzerdefinierten Formatzeichenfolgen in einem Steuerelement f&#252;r die Datums- und Zeitauswahl"
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
  - "CDateTimeCtrl-Klasse, Anzeigestile"
  - "DateTimePicker-Steuerelement [MFC]"
  - "DateTimePicker-Steuerelement [MFC], Anzeigestile"
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von benutzerdefinierten Formatzeichenfolgen in einem Steuerelement f&#252;r die Datums- und Zeitauswahl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig werden Steuerelemente für die Datums\- und Zeitauswahl drei Formattypen \(die einzelnen Stile entsprechend einem eindeutigen Format\) zum Anzeigen des aktuellen Datums bereit oder Entsperren Zeit fest:  
  
-   **DTS\_LONGDATEFORMAT** wird das Datum im langen Format an und erzeugt ausgegeben wie "am Mittwoch, den 3. Januar 2000".  
  
-   **DTS\_SHORTDATEFORMAT** wird das Datum des kurzen Format an und erzeugt ausgegeben wie "1\/3\/00".  
  
-   **DTS\_TIMEFORMAT** wird die Zeit im langen Format an und leitet erzeugt z "5:31: 42 PM".  
  
 Sie können die Darstellung des Datums oder einer Uhrzeit anpassen, indem Sie eine benutzerdefinierte Formatzeichenfolge verwenden.  Diese benutzerdefinierte Zeichenfolge besteht entweder vorhandene Formatzeichen, Internformatzeichen oder eine Kombination aus beidem.  Sobald die benutzerdefinierte Zeichenfolge erstellt wird, können Sie [CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md) einen Aufruf, das in die benutzerdefinierte Zeichenfolge einfügen.  Das Steuerelement für die Datums\- und Zeitauswahl wird der aktuelle Wert mithilfe der benutzerdefinierten Formatzeichenfolge an.  
  
 Das folgende Codebeispiel \(wobei `m_dtPicker` das `CDateTimeCtrl`\-Objekt ist, wird eine mögliche Lösung:  
  
 [!CODE [NVC_MFCControlLadenDialog#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#7)]  
  
 Zusätzlich zu den benutzerdefinierten Formatzeichenfolgen unterstützen Steuerelemente für die Datums\- und Zeitauswahl auch [Rückruffelder](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)