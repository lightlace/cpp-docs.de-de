---
title: "strtod, _strtod_l, wcstod, _wcstod_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstod"
  - "_wcstod_l"
  - "_strtod_l"
  - "strtod"
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
  - "_tcstod"
  - "strtod"
  - "wcstod"
  - "_strtod_l"
  - "_wcstod_l"
  - "stdlib/strtod"
  - "corecrt_wstdlib/wcstod"
  - "stdlib/_strtod_l"
  - "corecrt_wstdlib/_wcstod_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtod_l-Funktion"
  - "_tcstod-Funktion"
  - "_tcstod_l-Funktion"
  - "_wcstod_l-Funktion"
  - "Zeichenfolgenkonvertierung, in Gleitkommawerte"
  - "strtod-Funktion"
  - "strtod_l-Funktion"
  - "tcstod-Funktion"
  - "tcstod_l-Funktion"
  - "wcstod-Funktion"
  - "wcstod_l-Funktion"
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# strtod, _strtod_l, wcstod, _wcstod_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertieren von Zeichenfolgen in einen Wert mit doppelter Genauigkeit.  
  
## Syntax  
  
```  
double strtod(  
   const char *nptr,  
   char **endptr   
);  
double _strtod_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
double wcstod(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
double wcstod_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `nptr`  
 Zu konvertierende mit NULL endende Zeichenfolge.  
  
 `endptr`  
 Zeiger auf ein Zeichen, mit dem die Überprüfung beendet wird.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 `strtod` gibt den Wert der Gleitkommazahl zurück, ausgenommen, die Darstellung führt zu einem Überlauf. In diesem Fall gibt die Funktion \+\/\-`HUGE_VAL` zurück.  Das Zeichen von `HUGE_VAL` entspricht dem Zeichen des Werts, der nicht angezeigt werden kann.  `strtod` gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann oder ein Unterlauf auftritt.  
  
 `wcstod` gibt Werte analog zu `strtod` zurück.  `errno` wird für beide Funktionen auf `ERANGE` gesetzt, wenn ein Überlauf oder ein Unterlauf auftritt und der Handler für ungültige Parameter aufgerufen wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Siehe [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) weitere Informationen über diese und andere. Rückgabecodes  
  
## Hinweise  
 Jede Funktion wandelt die Eingabezeichenfolge `nptr` in einen `double`\-Wert um.  Die `strtod`\-Funktion konvertiert `nptr` in einen Wert mit doppelter Genauigkeit.  `strtod` stoppt das Lesen der `nptr`\-Zeichenfolge beim ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dies ist möglicherweise das beendende NULL\-Zeichen.  `wcstod` ist eine Breitzeichenversion von `strtod`. Das dazugehörige `nptr`\-Argument ist eine Breitzeichenfolge.  Anderenfalls verhalten sich diese Funktionen identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcstod`|`strtod`|`strtod`|`wcstod`|  
|`_tcstod_l`|`_strtod_l`|`_strtod_l`|`_wcstod_l`|  
  
 Die `LC_NUMERIC` Kategorieneinstellung des aktuellen Gebietsschemas bestimmt Erkennung des Basiszeichen in `nptr`*;* Weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Features ohne das Suffix `_l` verwenden das aktuelle Gebietsschema; `_strtod_l` ist mit `_strtod_l` identisch, allerdings verwenden das Gebietsschema, das ein\- stattdessen übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Wenn `endptr` nicht `NULL` ist, wird ein Zeiger auf das Zeichen, das die Überprüfung beendet hat, an dem Ort gespeichert, auf den durch `endptr` gezeigt wird.  Wenn keine Konvertierung ausgeführt werden kann \(keine gültigen Ziffern gefunden oder ungültige Basis angegeben\), wird der Wert von `nptr` an dem Speicherort gespeichert, auf den durch `endptr` gezeigt wird.  
  
 `strtod` erwartet, dass `nptr` auf eine Zeichenfolge der folgenden Form zeigt:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E`}\[`sign`\]`digits`\]  
  
 `whitespace` besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden; `sign` ist entweder Pluszeichen \(`+`\) oder Minuszeichen \(`–`\); and `digits` sind eine oder mehrere Dezimalstellen.  Wenn keine Ziffern vor dem Basiszeichen stehen, muss mindestens eine Ziffer nach dem Basiszeichen stehen.  Auf die Dezimalstellen kann ein Exponent folgen, der aus einem einführenden Buchstaben \(`d`, `D`, `e` oder `E`\) und einer optional Zahl mit Vorzeichen besteht.  Wenn weder ein Exponententeil noch ein Basiszeichen angezeigt wird, wird davon ausgegangen, dass ein Basiszeichen auf die letzte Ziffer in der Zeichenfolge folgt.  Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strtod`, `_strtod_l`|\<stdlib.h\>|  
|`wcstod`, `_wcstod_l`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_strtod.c  
// This program uses strtod to convert a  
// string to a double-precision value; strtol to  
// convert a string to long integer values; and strtoul  
// to convert a string to unsigned long-integer values.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char   *string, *stopstring;  
   double x;  
   long   l;  
   int    base;  
   unsigned long ul;  
  
   string = "3.1415926This stopped it";  
   x = strtod( string, &stopstring );  
   printf( "string = %s\n", string );  
   printf("   strtod = %f\n", x );  
   printf("   Stopped scan at: %s\n\n", stopstring );  
  
   string = "-10110134932This stopped it";  
   l = strtol( string, &stopstring, 10 );  
   printf( "string = %s\n", string );  
   printf("   strtol = %ld\n", l );  
   printf("   Stopped scan at: %s\n\n", stopstring );  
  
   string = "10110134932";  
   printf( "string = %s\n", string );  
  
   // Convert string using base 2, 4, and 8:  
   for( base = 2; base <= 8; base *= 2 )  
   {  
      // Convert the string:  
      ul = strtoul( string, &stopstring, base );  
      printf( "   strtol = %ld (base %d)\n", ul, base );  
      printf( "   Stopped scan at: %s\n", stopstring );  
   }  
}  
```  
  
  **\= Zeichenfolge 3.1415926This beendeten es**  
 **strtod \= 3,141593**  
 **Stopped scan at: This stopped it**  
**\= Zeichenfolge \-10110134932This beendeten es**  
 **strtol \= \-2147483648**  
 **Stopped scan at: This stopped it**  
**Zeichenfolge \= 10110134932**  
 **strtol \= 45 \(Basis 2\)**  
 **Beendeter Überprüfung an: 34932**  
 **strtol \= 4423 \(Basis 4\)**  
 **Beendeter Überprüfung an: 4932**  
 **strtol \= 2134108 \(Basis 8\)**  
 **Beendeter Überprüfung an: 932**   
## .NET Framework-Entsprechung  
 [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)