---
title: "fcvt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fcvt"
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
  - "fcvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fcvt-Funktion"
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _fcvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Gleitkommazahl zu einer Zeichenfolge.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md).  
  
## Syntax  
  
```  
char *_fcvt(   
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
 Anzahl der Ziffern nach dem Dezimalkomma.  
  
 `dec`  
 Zeiger zur gespeicherten Kommastellung.  
  
 `sign`  
 Zeiger zum gespeicherten Zeichenindikator.  
  
## Rückgabewert  
 `_fcvt` gibt einen Zeiger zur Zeichenfolge der Ziffern, NULL in Fehler zurück.  
  
## Hinweise  
 Die `_fcvt`\-Funktion konvertiert eine Gleitkommazahl zu einer auf NULL endende Zeichenfolge.  Der `value`\-Parameter ist die zu konvertierende, Gleitkommazahl.  `_fcvt` speichert die Ziffern von `value` als Zeichenfolge und fügt an ein NULL\-Zeichen \("\\ 0 "\).  Der `count`\-Parameter gibt die Anzahl der nach dem Dezimaltrennzeichen an zu speichernden Ziffern.  Überschüssige Ziffern werden `count` weg zu Stellen gerundet.  Wenn es weniger als `count` Ziffern von Genauigkeit gibt, wird die Zeichenfolge durch Nullen ergänzt.  
  
 Die Gesamtzahl von Ziffern, die von `_fcvt` zurückgegeben werden, überschreitet nicht `_CVTBUFSIZE`.  
  
 Nur Ziffern sind in der Zeichenfolge gespeichert.  Die Position des Dezimaltrennzeichens und das Zeichen von `value` können von `dec` und dem Zeichen nach dem Aufruf abgerufen werden.  Der `dec`\-Parameter zeigt auf einen ganzzahligen Wert; dieser ganzzahlige Wert gibt die Position des Dezimaltrennzeichens in Bezug auf den Anfang der Zeichenfolge.  Ein null oder negative ganzzahliger Wert gibt an, dass das Dezimaltrennzeichen auf der linken Seite die erste Ziffer liegt.  Der Parameter `sign` zeigt auf eine ganze Zahl, die das Zeichen von `value` angibt.  Die ganze Zahl wird 0 festgelegt, wenn `value` gleich ist und wird auf eine Zahl ungleich 0 \(null\) festgelegt, wenn `value` negativ ist.  
  
 Der Unterschied zwischen `_ecvt` und `_fcvt` ist in der Interpretation des Parameters `count`.  `_ecvt` interpretiert `count` während die Gesamtzahl der Stellen in der Ausgabezeichenfolge, während `_fcvt``count` als Anzahl von Ziffern nach dem Dezimaltrennzeichen interpretiert.  
  
 `_ecvt` und `_fcvt` verwenden einen statisch einzelnen zugeordneten Puffer für die Konvertierung.  Jeder Aufruf bis eine dieser Routinen zerstört die Ergebnisse des vorherigen Aufrufs.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `dec` oder `sign` ist NULL oder `count` 0 ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno` auf `EINVAL` festgelegt und NULL wird zurückgegeben.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fcvt`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fcvt.c  
// compile with: /W3  
// This program converts the constant  
// 3.1415926535 to a string and sets the pointer  
// buffer to point to that string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  decimal, sign;  
   char *buffer;  
   double source = 3.1415926535;  
  
   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996  
   // Note: _fcvt is deprecated; consider using _fcvt_s instead  
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",  
            source, buffer, decimal, sign );  
}  
```  
  
  **Quelle: Puffer 3,1415926535: "31415927 " decimal: 1 Zeichen: 0**   
## .NET Framework-Entsprechung  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)