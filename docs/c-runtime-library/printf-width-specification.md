---
title: "printf-Breitenangabe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "printf-Funktion, Formatangabefelder"
  - "printf-Funktion, Breitenspezifikation"
ms.assetid: 8b4a1b1e-bf6e-414f-a1b6-a9b6f1b6ce92
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# printf-Breitenangabe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einer Formatangabe ist die zweite optionales Feld die Breitenangabe.  Das Argument `width` ist eine nicht negative ganze Dezimalzahl, der die Mindestanzahl von Zeichen gesteuert wird, die ausgegeben werden.  Wenn die Anzahl der Zeichen im Ausgabewert kleiner als die angegebene Breite ist, werden Leerzeichen rechts nach links oder dafür Wert\-abhängen hinzugefügt, ob das linke Ausrichtungsflag \(`-`\) ist, angegebene\-bis die Mindestbreite erreicht wird.  Wenn `width` von 0 vorangestellt wird, werden führende Nullen in ganzzahlige oder Gleitkommakonvertierungen hinzugefügt, bis die Mindestbreite erreicht ist, außer, wenn eine Konvertierung nach unendlich entspricht oder ein NAN ist.  
  
 Die Breitenangabe wird niemals ein Wert abgeschnitten werden.  Wenn die Anzahl der Zeichen im Ausgabewert größer als die angegebene Breite ist oder wenn `width` nicht angegeben ist, werden alle Zeichen des Werts nach der Spezifikation [Genauigkeit](../c-runtime-library/precision-specification.md) ausgegeben.  
  
 Wenn die Breitenangabe ein Sternchen \(`*`\) ist, stellt `int` ein Argument aus der Argumentliste den Wert.  Das `width`\-Argument muss dem Wert, der in der Argumentliste formatiert wird, wie in diesem Beispiel gezeigt angeben:  
  
 `printf("%0*f", 5, 3);  /* 00003 is output */`  
  
 Ein "Fehlt" kleiner oder ein `width`\-Wert in einer Formatangabe verursacht nicht das Zuschneiden eines Ausgabewerts.  Wenn das Ergebnis einer Konvertierung breiter als `width`\-Wert ist, gilt das Kontrollkästchen, um das Konvertierungsergebnis zu enthalten.  
  
## Siehe auch  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Flag\-Direktiven](../c-runtime-library/flag-directives.md)   
 [Genauigkeitsangabe](../c-runtime-library/precision-specification.md)   
 [Größenangabe](../c-runtime-library/size-specification.md)   
 [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md)