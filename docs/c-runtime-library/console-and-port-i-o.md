---
title: "Konsole und Port-E/A"
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
  - "c.io"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "E/A [CRT], Konsole"
  - "E/A [CRT], Port"
  - "E/A-Routinen, Konsole und Port-E/A"
  - "Anschlüsse, E/A-Routinen"
  - "Routinen"
  - "Routinen, Konsole und Port-E/A"
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Konsole und Port-E/A
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lesen dieser Routinen und schreibt auf die Konsole oder den angegebenen Anschluss.  Die Konsole E\/A\-Routinen nicht mit Stream\-E\/A oder E\/A\-Bibliotheksroutinen systemnahe kompatibel.  Die Konsole oder der Port muss nicht geöffnet sein, oder geschlossen wurden, bevor E\/A ausgeführt wird, so wird keine offenen oder schließende Routinen in diese Kategorie.  In den Windows\-Betriebssystemen wird die Ausgabe dieser Funktionen immer auf die Konsole verwiesen und kann nicht weitergeleitet werden.  
  
### Konsole und Port E\/A Routinen  
  
|Routine|Verwendung|  
|-------------|----------------|  
|[\_cgets, \_cgetws](../c-runtime-library/cgets-cgetws.md), [\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Lesezeichenfolge der Konsole|  
|[\_cprintf, \_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|zum formatierte Daten, um zu trösten|  
|[\_cputs](../c-runtime-library/reference/cputs-cputws.md)|Schreiben Sie in der Konsole Zeichenfolge|  
|[\_cscanf, \_cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Lesen formatierte Daten der Konsole|  
|[\_getch, \_getwch](../c-runtime-library/reference/getch-getwch.md)|Lesezeichen aus der Konsole|  
|[\_getche, \_getwche](../c-runtime-library/reference/getch-getwch.md)|Lesen von Zeichen aus der Konsole und geben Sie es Echo aus|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|Lesen ein Byte vom angegebenen E\/A\-Anschluss|  
|[\_inpd](../c-runtime-library/inp-inpw-inpd.md)|Lesedoppelwort vom angegebenen E\/A\-Anschluss|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|Lese2\-byte\-Wort vom angegebenen E\/A\-Anschluss|  
|[\_kbhit](../c-runtime-library/reference/kbhit.md)|Überprüfung Tastatureingabe an der Konsole; Verwendung bevor Sie versuchen, in der Konsole lesen|  
|[\_outp](../c-runtime-library/outp-outpw-outpd.md)|Schreiben Sie ein Byte dem angegebenen E\/A\-Anschluss|  
|[\_outpd](../c-runtime-library/outp-outpw-outpd.md)|Schreiben Sie Doppelwort dem angegebenen E\/A\-Anschluss|  
|[\_outpw](../c-runtime-library/outp-outpw-outpd.md)|Schreiben Sie Wort dem angegebenen E\/A\-Anschluss|  
|[\_putch, \_putwch](../c-runtime-library/reference/putch-putwch.md)|Schreiben von Zeichen auf der Konsole|  
|[\_ungetch, \_ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|Lesen letzten Zeichens "Unget" von der Konsole und davon wird folgendes Zeichenlesen|  
  
## Siehe auch  
 [Eingabe und Ausgabe](../c-runtime-library/input-and-output.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)