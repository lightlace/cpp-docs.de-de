---
title: "ecvt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ecvt"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "ecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ecvt-Funktion"
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _ecvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert `double` eine Zahl in eine Zeichenfolge.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md).  
  
## Syntax  
  
```  
char *_ecvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### Parameter  
 `value`  
 Zu konvertierende Zahl.  
  
 `count`  
 Zahl Ziffern gespeichert.  
  
 `dec`  
 Gespeicherte Kommastellung.  
  
 `sign`  
 Zeichen der konvertierten Zahl.  
  
## Rückgabewert  
 `_ecvt` gibt einen Zeiger zur Zeichenfolge aus Ziffern zurück; MAKE ungültig, wenn ein Fehler aufgetreten ist.  
  
## Hinweise  
 Die `_ecvt`\-Funktion konvertiert eine Gleitkommazahl zu einer Zeichenfolge.  Der `value`\-Parameter ist die zu konvertierende, Gleitkommazahl.  Diese Funktion speichert bis `count` Ziffern von `value` als Zeichenfolge und fügt an ein NULL\-Zeichen \("\\ 0 "\).  Wenn die Anzahl der Ziffern in `value``count` überschreitet, wird die Ziffer niederwertige gerundet.  Wenn es weniger als Ziffern `count` gibt, wird die Zeichenfolge durch Nullen ergänzt.  
  
 Die Gesamtzahl von Ziffern, die von `_ecvt` zurückgegeben werden, überschreitet nicht `_CVTBUFSIZE`.  
  
 Nur Ziffern sind in der Zeichenfolge gespeichert.  Die Position des Dezimaltrennzeichens und das Zeichen von `value` können von `dec` und `sign` nach dem Aufruf abgerufen werden.  Der `dec`\-Parameter zeigt auf einen ganzzahligen Wert, der die Position des Dezimaltrennzeichens in Bezug auf den Anfang der Zeichenfolge vorhanden sind.  0 oder ein ganzzahliger negativer Wert gibt an, dass das Dezimaltrennzeichen auf der linken Seite die erste Ziffer liegt.  Der `sign`\-Parameter zeigt auf eine ganze Zahl, die das Zeichen der konvertierten Zahl angibt.  Wenn der ganzzahlige Wert 0 ist, wird die Zahl positiv.  Andernfalls ist die Zahl negativ.  
  
 Der Unterschied zwischen `_ecvt` und `_fcvt` ist in der Interpretation des Parameters `count`.  `_ecvt` interpretiert `count` während die Gesamtzahl der Stellen in der Ausgabezeichenfolge, während `_fcvt``count` als Anzahl von Ziffern nach dem Dezimaltrennzeichen interpretiert.  
  
 `_ecvt` und `_fcvt` verwenden einen statisch einzelnen zugeordneten Puffer für die Konvertierung.  Jeder Aufruf bis eine dieser Routinen zerstört das Ergebnis der vorherigen Aufrufs.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `dec` oder `sign` ist NULL oder `count` 0 ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno` auf `EINVAL` festgelegt und NULL wird zurückgegeben.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_ecvt`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
  **Quelle: Puffer 3,1415926535: "3141592654 " decimal: 1 Zeichen: 0**   
## .NET Framework-Entsprechung  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)