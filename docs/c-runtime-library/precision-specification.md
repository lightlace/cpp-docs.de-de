---
title: "Genauigkeitsangabe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "printf-Funktion, Formatangabefelder"
ms.assetid: dc59ea4e-d23a-4f1f-9881-2c919ebefb82
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Genauigkeitsangabe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einer Formatangabe ist das dritte optionales Feld die Genauigkeitsspezifikation.  Es besteht aus einem Punkt \(.\) gefolgt von dezimalen eine nicht negative ganze Zahl, die, abhängig vom Konvertierungstyp, der Anzahl von Zeichenfolgen, die Anzahl an Dezimalstellen oder die Anzahl der signifikanten ausgegeben werden angibt Ziffern.  
  
 Anders als die Breitenangabe kann die Genauigkeitsspezifikation jedes Verkürzung eines Ausgabewerts oder des Rundens eines Gleitkommawerts verursachen.  Wenn `precision` angegeben ist, zu 0 und der zu konvertierende Wert 0 ist, ist das Ergebnis nicht Zeichenausgabe, wie in diesem Beispiel dargestellt:  
  
 `printf( "%.0d", 0 );      /* No characters output */`  
  
 Wenn die Genauigkeitsspezifikation ein Sternchen \(\*\), bietet `int` ein Argument aus der Argumentliste den Wert.  In der Argumentliste muss das `precision`\-Argument den Wert, der formatiert wird, wie in diesem Beispiel gezeigt angeben:  
  
 `printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`  
  
 Der Typ bestimmt entweder die Interpretation von `precision` oder die Standardgenauigkeit, wenn `precision` weggelassen wird, wie in der folgenden Tabelle gezeigt.  
  
### Wie Genauigkeits\-Wert\-Affekt\-Typ  
  
|Typ|Bedeutung|Default|  
|---------|---------------|-------------|  
|`a`, `A`|Die Genauigkeit gibt die Anzahl von Ziffern nach dem Punkt an.|Standardgenauigkeit ist. 6.  Wenn Genauigkeit 0 ist, wird kein Dezimaltrennzeichen gedruckt, es sei denn, das `#`\-Flag verwendet wird.|  
|`c`, `C`|Die Genauigkeit hat keine Auswirkungen.|Zeichen wird ausgegeben.|  
|`d`, `i`, `u`, `o`, `x`, `X`|Die Genauigkeit gibt die gewünschte Mindestanzahl von den zu druckende, Ziffern an.  Wenn die Anzahl der Ziffern im Argument kleiner als `precision` ist, wird der Ausgabewert nach links mit Nullen ergänzt.  Der Wert wird nicht verkürzt, wenn die Anzahl der Ziffern `precision` überschreitet.|Standardgenauigkeit ist. 1.|  
|`e`, `E`|Die Genauigkeit gibt die Anzahl der nach dem Dezimaltrennzeichen an zu druckende Ziffern.  Die letzte gedruckte Ziffer wird gerundet.|Standardgenauigkeit ist. 6.  Wenn `precision` 0 ist, oder der Punkt \(.\) ohne eine Zahl angezeigt, die darauf folgt, kein Dezimaltrennzeichen gedruckt.|  
|`f`|Der Genauigkeitswert gibt die Anzahl von Ziffern nach dem Dezimaltrennzeichen an.  Wenn ein Dezimaltrennzeichen wird, mindestens wird eine Ziffer vor ihr.  Der Wert wird die entsprechende Anzahl der Ziffern gerundet.|Standardgenauigkeit ist. 6.  Wenn `precision` 0 ist oder wenn der Punkt \(.\) ohne eine Zahl angezeigt, die darauf folgt, kein Dezimaltrennzeichen gedruckt.|  
|`g`, `G`|Die Genauigkeit gibt die maximale Anzahl von signifikanten gedruckten Ziffern angezeigt.|Sechs signifikante Stellen ausgegeben werden, und alle nachfolgenden Nullen werden abgeschnitten.|  
|`s`, `S`|Die Genauigkeit gibt die maximale Anzahl der zu druckende an Zeichen.  Zeichen mehr als `precision` werden nicht gedruckt.|Zeichen werden ausgegeben, bis ein NULL\-Zeichen aufgetreten ist.|  
  
## Siehe auch  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Flag\-Direktiven](../c-runtime-library/flag-directives.md)   
 [printf\-Breitenangabe](../c-runtime-library/printf-width-specification.md)   
 [Größenangabe](../c-runtime-library/size-specification.md)   
 [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md)