---
title: "Formatangabefelder: scanf- und wscanf-Funktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wscanf"
  - "scanf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Breite, Spezifikationen in scanf-Funktion"
  - "scanf-Formatangaben"
  - "scanf-Breitenangaben"
  - "scanf-Typenfeldzeichen"
  - "Typfelder, scanf-Funktion"
  - "Formatangabefelder für scanf-Funktion"
  - "type-Felder"
ms.assetid: 7e95de1b-0b71-4de3-9f81-c9560c78e039
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Formatangabefelder: scanf- und wscanf-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Informationen hier anzuwenden gesamte `scanf` \- Familie von Funktionen, einschließlich die sicheren Versionen und beschreiben die Symbole, die verwendet werden, um den `scanf`\-Funktionen mitzuteilen, wie den Eingabestream Eingabestream, wie der `stdin` für `scanf`, in Werte analysiert, die in Programmvariablen eingefügt werden.  
  
 Eine Formatangabe hat das folgende Format:  
  
 `%`\[`*`\] \[[Breite](../c-runtime-library/scanf-width-specification.md)\] \[{[h &#124; L &#124; ll &#124; I64 &#124; L](../c-runtime-library/scanf-width-specification.md)}\][Typ](../c-runtime-library/scanf-type-field-characters.md)  
  
 Das Argument `format` gibt der Interpretation der Eingabe an und kann eine oder mehrere der folgenden enthalten:  
  
-   Leerzeichen: Leerzeichen \(" "\); Registerkarte \("\\t"\); oder Zeilenumbruch \("\\n"\).  Ein Leerzeichen wird `scanf` lesen, jedoch nicht gespeichert, alle nachfolgenden Leerzeichen in der Eingabe bis zum nächsten Nicht\-Leerzeichen.  Ein Leerzeichen im Format entspricht eine Zahl \(einschließlich 0\) und Kombination von Leerzeichen in der Eingabe ab.  
  
-   Nicht\-weiß\-Leerzeichenzeichen, außer dem Prozentzeichen \(`%`\).  Ein Nicht\-Leerzeichen bewirkt `scanf` lesen, jedoch nicht Speicher, ein passendes Nicht\-Leerzeichen.  Wenn das nächste Zeichen im Eingabestream nicht entspricht, endet `scanf`.  
  
-   Formatangaben, eingeführt durch das Prozentzeichen \(`%`\).  Eine Formatangabe veranlasst, dass `scanf` Zeichen in der Eingabe in Werte eines bestimmten Typs zu lesen und zu konvertieren.  Der Wert wird auf ein Argument in der Argumentliste zugewiesen.  
  
 Das Format wird von links nach rechts gelesen.  Zeichen außerhalb der Formatangaben werden erwartet, die Reihenfolge der Zeichen im Eingabestream entspricht; die entsprechenden Zeichen im Eingabestream werden überprüft, jedoch nicht gespeichert.  Wenn ein Zeichen im Eingabestream mit der Formatangabe verursacht, endet `scanf`, und das Zeichen im Eingabestream wird links, als ob sie nicht gelesen wurde.  
  
 Wenn die erste Formatangabe erreicht wird, wird der Wert des ersten Eingabefelds entsprechend dieser Spezifikation konvertiert und dem Speicherort, von der ersten `argument` angegeben wird.  Die zweite Formatangabe wird das zweite Bearbeitungsfeld, im zweiten `argument`, z. B. vom Ende der Formatzeichenfolge zu konvertierende und gespeichert.  
  
 Ein Bearbeitungsfeld wird als alle Zeichen bis zum ersten Leerzeichen \(Leerzeichen, Tabulatorzeichen oder Zeilenumbruch\) oder bis zum ersten Zeichen definiert, die nicht entsprechend der Formatangabe konvertiert werden kann, oder bis die Feldbreite \(sofern angegeben\) wird erreicht.  Wenn zu viele Argumente für die angegebene Spezifikation gibt, werden die zusätzlichen Argumente ausgewertet, aber ignoriert.  Die Ergebnisse sind unvorhersehbar, wenn nicht genügend Argumente für die Formatangabe gibt.  
  
 Jedes Feld der Formatangabe ist ein einzelnes Zeichen oder einer Zahl, die einer bestimmten Formatoption angeben.  Das `type` Zeichen, das nach dem letzten Formatfeld optionale wird, bestimmt, ob das Eingabefeld als Zeichen oder Zeichenfolge, Zahl interpretiert wird.  
  
 Die einfachste Formatangabe enthält nur das Prozentzeichen und ein `type` Zeichen \(beispielsweise, `%s`\).  Wenn ein Prozentzeichen \(`%`\) von einem Zeichen folgt, das keine Bedeutung als FormatSteuerelementzeichen verfügt, werden diese Zeichen und die folgenden Zeichen \(bis zum folgenden Prozentzeichen\) als gewöhnliche Sequenz von Zeichen. d. h. eine Folge von Zeichen behandelt, die die Eingabe übereinstimmen müssen.  beispielsweise angeben, dass ein Prozentzeichen eingegeben werden soll, verwenden Sie `%%`.  
  
 Ein Sternchen \(`*`\) das Prozentzeichen Nachfolgeereignis unterdrückt Zuweisung des folgenden Eingabefelds, das während ein Feld des angegebenen Typs interpretiert wird.  Das Feld wird überprüft, jedoch nicht gespeichert.  
  
 Die sicheren Versionen \(die mit dem Suffix `_s` \) der `scanf` \- Familie von Funktionen erfordern, die ein Puffergrößenparameter direkt nach jedem Parameter des Typs `c`, `C`, `s`, `S` oder `[` übergeben wird.  Weitere Informationen zum sicheren Versionen der `scanf` \- Familie von Funktionen, finden Sie unter [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md).  
  
## Siehe auch  
 [scanf\-Breitenangabe](../c-runtime-library/scanf-width-specification.md)   
 [scanf\-Typenfeldzeichen](../c-runtime-library/scanf-type-field-characters.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)