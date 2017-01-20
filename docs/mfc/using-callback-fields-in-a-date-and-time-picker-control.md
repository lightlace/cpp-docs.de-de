---
title: "Verwenden von R&#252;ckruffeldern in einem Steuerelement f&#252;r die Datums- und Zeitauswahl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "DTN_FORMATQUERY"
  - "DTN_FORMAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rückruffelder in CDateTimeCtrl-Klasse"
  - "CDateTimeCtrl-Klasse, Rückruffelder"
  - "CDateTimeCtrl-Klasse, Behandeln von DTN_FORMAT und DTN_FORMATQ"
  - "DateTimePicker-Steuerelement [MFC]"
  - "DateTimePicker-Steuerelement [MFC], Rückruffelder"
  - "DTN_FORMAT-Benachrichtigung"
  - "DTN_FORMATQUERY-Benachrichtigung"
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von R&#252;ckruffeldern in einem Steuerelement f&#252;r die Datums- und Zeitauswahl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zusätzlich zu den Standardformatzeichen, die Datums\- Zeitauswahl\-Felder definieren, können Sie die Ausgabe anpassen, indem Sie bestimmte Teile einer benutzerdefinierten Formatzeichenfolge als Rückruffelder angeben.  Um ein Rückruffeld zu deklarieren, eine oder mehrere "X Zeichen \(ASCII codiert 88\) überall im Text der Formatzeichenfolge ein.  Beispielsweise wurde die folgende Zeichenfolge ""Today is: "yy "\/"MM "\/"dd" \(Tag "X "\)" wird das Steuerelement für die Datums\- und Zeitauswahl, den aktuellen Wert als das Jahr anzuzeigen, das nach den Monat folgt, wurde und schließlich der Tag des Jahrs.  
  
> [!NOTE]
>  Die Zahl von X auf einem Rückrufgebiet entspricht nicht zur Anzahl von Zeichen, die angezeigt werden.  
  
 Sie können zwischen mehreren Rückruffeldern in einer benutzerdefinierten Zeichenfolge unterscheiden, indem Sie das "X Zeichen überprüfen.  Daher enthält die Formatzeichenfolge "XXddddMMMdd, 'yyyXXX" zwei eindeutige Rückruffelder, "XX" und "USW.".  
  
> [!NOTE]
>  Rückruffelder werden als gültige Felder behandelt, daher muss die Anwendung darauf vorbereitet sein, **DTN\_WMKEYDOWN**  Benachrichtigungen bearbeiten.  
  
 Das Implementieren von Rückruffeldern im Steuerelement für die Datums\- und Zeitauswahl besteht aus drei Teilen:  
  
-   Initialisieren der benutzerdefinierten Formatzeichenfolge  
  
-   Behandeln der **DTN\_FORMATQUERY** Benachrichtigung  
  
-   Behandeln der **DTN\_FORMAT** Benachrichtigung  
  
## Initialisieren der benutzerdefinierten Formatzeichenfolge  
 Initialisieren Sie die benutzerdefinierte Zeichenfolge mit einem Aufruf von `CDateTimeCtrl::SetFormat`.  Weitere Informationen finden Sie unter [Verwenden von benutzerdefinierten Formatzeichenfolgen in einem Steuerelement für die Datums\- und Zeitauswahl](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md).  Ein allgemeiner Position, an der benutzerdefinierten Formatzeichenfolge festzulegen ist in der `OnInitDialog` der enthaltenden Funktion Dialogfeldklasse `OnInitialUpdate` oder Funktion der enthaltenden Ansichtsklasse.  
  
## Behandeln der DTN\_FORMATQUERY\-Benachrichtigung  
 Wenn das Steuerelement die Formatzeichenfolge analysiert und ein Rückruffeld trifft, sendet die Anwendung **DTN\_FORMAT** und **DTN\_FORMATQUERY** Benachrichtigungsmeldungen.  Die Rückruffeldzeichenfolge ist den Benachrichtigungen enthalten, sodass Sie ermitteln, das Rückruffeld abgefragt wird.  
  
 **DTN\_FORMATQUERY** Die Benachrichtigung wird gesendet, dass die maximal zulässige Größe in Pixel der Zeichenfolge abzurufen, die im aktuellen Rückrufgebiet angezeigt wird.  
  
 Um diesen Wert ordnungsgemäß zu berechnen, müssen Sie die Höhe und Breite der Zeichenfolge werden, für das Feld, mit der Anzeigenschriftart des Steuerelements ersetzt werden.  Die tatsächliche Berechnung der Zeichenfolge wird leicht mit einem Aufruf der [GetTextExtentPoint32](http://msdn.microsoft.com/library/windows/desktop/dd144938)\-Funktion von Win32 erreicht.  Sobald die Größe bestimmt, den Wert in der Anwendung besteht und beendet die Handlerfunktion.  
  
 Im folgenden Beispiel ist eine Angabe der Größe der Rückrufzeichenfolge:  
  
 [!CODE [NVC_MFCControlLadenDialog#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#8)]  
  
 Sobald sich die Größe des aktuellen Rückruffelds, müssen Sie einen Wert für das Feld angeben berechnet wurden.  Dies wird im Handler für die **DTN\_FORMAT** \- Benachrichtigung erfolgt.  
  
## Behandeln der DTN\_FORMAT\-Benachrichtigung  
 **DTN\_FORMAT** Die Benachrichtigung wird von der Anwendung, um die Zeichenfolge zu erfragen verwendet, die ersetzt wird.  Das folgende Beispiel veranschaulicht eine mögliche Methode:  
  
 [!CODE [NVC_MFCControlLadenDialog#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#9)]  
  
> [!NOTE]
>  Der Zeiger auf die **NMDATETIMEFORMAT** \-Struktur wird gefunden, indem Sie den ersten Parameter des Benachrichtigungshandlers den richtigen Typ umwandeln.  
  
## Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)