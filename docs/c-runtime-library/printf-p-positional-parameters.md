---
title: "printf_p-Positionsparameter | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_p-Funktion, Positionale Parameter"
  - "printf_p-Funktion, Positionale Parameter"
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# printf_p-Positionsparameter
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Positionsparameter bieten die Möglichkeit, mithilfe einer Zahl anzugeben, welche Argumente in einem Feld in einer Formatzeichenfolge ersetzt werden sollen.  Die folgenden `printf`\-Positionsparameterfunktionen sind verfügbar:  
  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)  
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)  
  
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)  
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)  
  
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)  
 [\_cprintf\_p, \_cprintf\_p\_l, \_cwprintf\_p, \_cwprintf\_p\_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)  
  
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)  
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)  
  
 [vprintf, \_vprintf\_l, vwprintf, \_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
 [\_vprintf\_p, \_vprintf\_p\_l, \_vwprintf\_p, \_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)  
  
 [vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)  
 [\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)  
  
 [vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)  
 [\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)  
  
## Angeben von Positionsparametern  
  
##### Parameter\-Indizierung  
 Standardmäßig verhalten sich Positionsparameter und Nicht\-Positionsparameter identisch, wenn keine Positionsformatierung vorhanden ist.  Positionsparameter werden im Format „`%m$x`“ angegeben, wobei `m` eine numerische Ordinalzahl ist, die die Position des Parameters in der Liste der Parameter angibt und der Formatzeichenfolge vorausgeht, und  `x` ist der in der `printf`\-Funktion angegebene Typfeldzeichen\-Typ.  Die Parameter in der Liste sind indiziert, beginnend mit dem Wert 1 für das erste Element der Liste.  Weitere Informationen zu Typenfeldzeichen finden Sie unter [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md).  
  
 Ein Beispiel für dieses Verhalten:  
  
```  
_printf_p("%1$s %2$s", "November", "10");  
```  
  
 gibt Folgendes zurück:  
  
```  
November 10  
```  
  
 Die Reihenfolge der verwendeten Zahlen muss nicht mit der Reihenfolge der angegebenen Argumente übereinstimmen.  Daher ist Folgendes gültig:  
  
```  
_printf_p("%2$s %1$s", "November", "10");  
```  
  
 gibt Folgendes zurück:  
  
```  
10 November  
```  
  
 Anders als in traditionellen Formatzeichenfolgen, können Parameter mehrmals für die Formatierung verwendet werden, d. h.  
  
```  
_printf_p("%1$d times %1$d is %2$d", 10, 100);  
```  
  
 gibt Folgendes zurück:  
  
```  
10 times 10 is 100  
```  
  
 Allerdings müssen alle Argumente mindestens einmal in der Formatzeichenfolge verwendet werden.  
  
 Die maximale Anzahl von Positionsparametern, die in einer Formatzeichenfolge zulässig sind, ist durch `_ARGMAX` angegeben.  
  
##### Breite und Genauigkeit  
 Wenn das Symbol „\*“ verwendet wird, um anzugeben, dass die Breite und Genauigkeit von einem Argument bestimmt wird, muss die Position des Breiten\- oder des Genauigkeitswerts direkt nach dem „\*“\-Symbol vorkommen.  Beispiel:  
  
```  
_printf_p("%1$*2$s","Hello", 10);  
```  
  
 oder  
  
```  
_printf_p("%2$*1$s",10, "Hello");  
```  
  
##### Mischen von Positions\- und Nicht\-Positionsargumenten  
 Positionsparameter dürfen nicht mit Nicht\-Positionsparametern in der gleichen Formatzeichenfolge kombiniert werden.  `printf_p`\- und verwandte Funktionen unterstützen jedoch weiterhin Nicht\-Positionsparameter in Formatzeichenfolgen ohne Positionsparameter.  
  
## Beispiel  
  
```  
// positional_args.c  
// Positional arguments allow the specification of the order  
// in which arguments are consumed in a formatting string.  
  
#include <stdio.h>  
  
int main(int argc, char *argv[])  
{  
    int     i = 1,  
            j = 2,  
            k = 3;  
    double  x = 0.1,  
            y = 0.2,  
            z = 0.3;  
    char    *s1 = "abc",  
            *s2 = "def",  
            *s3 = "ghi";  
  
    // If positional arguments are unspecified,  
    // normal input order is used.  
    _printf_p("%d %d %d\n", i, j, k);  
  
    // Positional args are numbers indicating the  
    // argument enclosed in curly braces.  
    _printf_p("%3$d %1$d %2$d\n", i, j, k);  
  
    // The same positional argument may be reused.  
    _printf_p("%1$d %2$d %1$d\n", i, j);  
  
    _printf_p("%1$s %2$s %3$s\n", s1, s2, s3);  
  
    _printf_p("%3$s %1$s %2$s\n", s1, s2, s3);  
}  
```  
  
  **1 2 3**  
**3 1 2**  
**1 2 1**  
**abc def ghi**  
**ghi abc def**   
## Siehe auch  
 [printf\-Typenfeldzeichen](../c-runtime-library/printf-type-field-characters.md)   
 [printf\-Breitenangabe](../c-runtime-library/printf-width-specification.md)   
 [Genauigkeitsangabe](../c-runtime-library/precision-specification.md)