---
title: "Bearbeiten von Stilen"
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
  - "ES_READONLY"
  - "ES_WANTRETURN"
  - "ES_UPPERCASE"
  - "ES_NUMBER"
  - "ES_AUTOHSCROLL"
  - "ES_LOWERCASE"
  - "ES_RIGHT"
  - "ES_MULTILINE"
  - "ES_PASSWORD"
  - "ES_NOHIDESEL"
  - "ES_OEMCONVERT"
  - "ES_LEFT"
  - "ES_CENTER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bearbeiten von Stilen [MFC]"
  - "ES_AUTOHSCROLL-Konstante"
  - "ES_AUTOVSCROLL-Konstante"
  - "ES_CENTER-Konstante"
  - "ES_LEFT-Konstante"
  - "ES_LOWERCASE-Konstante"
  - "ES_MULTILINE-Konstante"
  - "ES_NOHIDESEL-Konstante"
  - "ES_NUMBER-Konstante"
  - "ES_OEMCONVERT-Konstante"
  - "ES_PASSWORD-Konstante"
  - "ES_READONLY-Konstante"
  - "ES_RIGHT-Konstante"
  - "ES_UPPERCASE-Konstante"
  - "ES_WANTRETURN-Konstante"
ms.assetid: e6291dd6-f2cb-4ce2-ac31-32272526625c
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Bearbeiten von Stilen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   Führt **ES\_AUTOHSCROLL** automatisch Text rechts durch 10 Zeichen wenn der Benutzer ein Zeichen eingibt am Ende der Zeile.  Wenn der Benutzer die EINGABETASTE drückt, führt das Steuerelement allen Text zurück an Position 0 angezeigt.  
  
-   Führt **ES\_AUTOVSCROLL** automatisch Text in einer Seite, wenn der Benutzer auf die letzte Zeile die EINGABETASTE drückt.  
  
-   Mittelpunkte **ES\_CENTER** Text in einem oder einzeiligen mehrzeiligen Bearbeitungssteuerelement.  
  
-   Richtet **ES\_LEFT** Text in einem oder einzeiligen mehrzeiligen Bearbeitungssteuerelement aus.  
  
-   **ES\_LOWERCASE** konvertiert alle Zeichen in Kleinbuchstaben, während sie in das Bearbeitungssteuerelement eingegeben werden.  
  
-   **ES\_MULTILINE** legt ein mehrzeiliges Bearbeitungssteuerelement fest. \(Der Standardwert ist einzelne Zeile.\) Wenn das **ES\_AUTOVSCROLL** Format angegeben ist, zeigt das Bearbeitungssteuerelement so viele Zeilen wie möglich an und übergibt einen vertikalen Bildlauf wenn der Benutzer die EINGABETASTE drückt.  Wenn **ES\_AUTOVSCROLL** nicht angegeben ist, zeigt das Bearbeitungssteuerelement so viele Zeilen wie möglich und Signaltone an, wenn die EINGABETASTE gedrückt wird, wenn keine Zeilen mehr angezeigt werden können.  Wenn das **ES\_AUTOHSCROLL** Format angegeben wird, führt das mehrzeilige Bearbeitungssteuerelement automatisch horizontalen Bildlaufleite wenn die Einfügemarke hinter den rechten Rand des Steuerelements wechselt.  Um eine neue Zeile zu beginnen, muss der Benutzer die EINGABETASTE drücken.  Wenn **ES\_AUTOHSCROLL** nicht angegeben ist, wird das Steuerelement automatisch seine Wörter zum Anfang der nächsten Zeile bei Bedarf ein; eine neue Zeile wird außerdem gestartet, wenn die EINGABETASTE gedrückt wird.  Die Position des Textumbruchs wird von der Fenstergröße bestimmt.  Wenn die Fenstergröße ändert, ändert die Textumbruchposition und der Text wird erneut angezeigt.  Mehrzeilige Bearbeitungssteuerelemente können über Bildlaufleisten verfügen.  Ein Bearbeitungssteuerelement mit Bildlaufleisten verarbeitet die eigenen Bildlaufleistenmeldungen.  Bearbeitungssteuerelemente ohne Bildlaufleisten führen einen Bildlauf wie oben beschrieben und verarbeiten alle Bildlaufmeldungen, die das übergeordnete Fenster gesendet werden.  
  
-   **ES\_NOHIDESEL** normalerweise, ein Bearbeitungssteuerelement blendet die Auswahl, wenn das Steuerelement den Eingabefokus verliert aus und kehrt die Auswahl um, wenn das Steuerelement den Eingabefokus erhält.  **ES\_NOHIDESEL** angibt, löscht diese Standardaktion.  
  
-   **ES\_NUMBER** lässt nur die in das Bearbeitungssteuerelement übergegangen wird, Ziffern.  
  
-   **ES\_OEMCONVERT** Text, der in das Bearbeitungssteuerelement eingegeben wird, wird vom ANSI\-Zeichensatz zum OEM\-Zeichensatz und dann zurück in ANSI konvertiert.  Dies stellt richtige Zeichenkonvertierung sicher, wenn die Anwendung die Windows\-Funktion `AnsiToOem` aufruft, um eine ANSI\-Zeichenfolge im Bearbeitungssteuerelement in OEM\-Zeichen zu konvertieren.  Dieses Format ist für Bearbeitungssteuerelemente besonders hilfreich, die Dateinamen enthalten.  
  
-   **ES\_PASSWORD** werden alle Zeichen wie Sternchen an \(**\***\) wie in das Bearbeitungssteuerelement eingegeben werden.  Eine Anwendung kann die `SetPasswordChar`\-Memberfunktion verwenden, um das Zeichen ändern, das angezeigt wird.  
  
-   **ES\_READONLY** verhindert der Benutzer ungültige Zahlen eingibt oder das Bearbeiten des Texts im Bearbeitungssteuerelement.  
  
-   **ES\_RIGHT** Recht\-richtet Text in einem oder einzeiligen mehrzeiligen Bearbeitungssteuerelement aus.  
  
-   **ES\_UPPERCASE** konvertiert alle Zeichen in Großbuchstaben, wie in das Bearbeitungssteuerelement eingegeben werden.  
  
-   **ES\_WANTRETURN** gibt an, dass ein Wagenrücklaufzeichen eingefügt wird, wenn der Benutzer beim Eingeben von Text in ein mehrzeiliges Bearbeitungssteuerelement in einem Dialogfeld die EINGABETASTE drückt.  Ohne dieses Format hat das Drücken der EINGABETASTE die gleichen Auswirkungen, dem, Dialogfelder drücken, Pushbutton den Standardwert aufweisen Sie.  Dieses Format hat keine Auswirkungen auf ein einzeiliges Bearbeitungssteuerelement.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CEdit::Create](../Topic/CEdit::Create.md)   
 [Edit Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb775464)