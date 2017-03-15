---
title: "strtof, _strtof_l, wcstof, _wcstof_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strtof_l"
  - "wcstof"
  - "strtof"
  - "_wcstof_l"
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
  - "_tcstof"
  - "_tcstof_l"
  - "stdlib/strtof"
  - "strtof"
  - "stdlib/_strtof_l"
  - "_strtof_l"
  - "corecrt_wstdlib/wcstof"
  - "wcstof"
  - "corecrt_wstdlib/_wcstof_l"
  - "_wcstof_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtof_l-Funktion"
  - "_tcstof-Funktion"
  - "_tcstof_l-Funktion"
  - "_wcstof_l-Funktion"
  - "strtof-Funktion"
  - "wcstof-Funktion"
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# strtof, _strtof_l, wcstof, _wcstof_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge in einen Gleitkommawert mit einfacher Genauigkeit.  
  
## Syntax  
  
```  
float strtof(  
   const char *nptr,  
   char **endptr   
);  
float _strtof_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
float wcstof(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
float wcstof_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `nptr`  
 Zu konvertierende mit NULL endende Zeichenfolge.  
  
 `endptr`  
 Zeiger auf das Zeichen, das die Überprüfung stoppt.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 `strtof` gibt den Wert der Gleitkommazahl zurück, ausgenommen, die Darstellung führt zu einem Überlauf. In diesem Fall gibt die Funktion \+\/\-`HUGE_VALF` zurück.  Das Zeichen von `HUGE_VALF` entspricht dem Zeichen des Werts, der nicht angezeigt werden kann.  `strtof` gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann oder ein Unterlauf auftritt.  
  
 `wcstof` gibt Werte analog zu `strtof` zurück.  `errno` wird für beide Funktionen auf `ERANGE` gesetzt, wenn ein Überlauf oder ein Unterlauf auftritt und der Handler für ungültige Parameter aufgerufen wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Weitere Informationen zu Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Jede Funktion wandelt die Eingabezeichenfolge `nptr` in einen `float`\-Wert um.  Die `strtof`\-Funktion konvertiert `nptr` in einen Wert mit einfacher Genauigkeit.  `strtof` stoppt das Lesen der `nptr`\-Zeichenfolge beim ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dies ist möglicherweise das beendende NULL\-Zeichen.  `wcstof` ist eine Breitzeichenversion von `strtof`. Das dazugehörige `nptr`\-Argument ist eine Breitzeichenfolge.  Ansonsten verhalten sich diese Funktionen identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcstof`|`strtof`|`strtof`|`wcstof`|  
|`_tcstof_l`|`_strtof_l`|`_strtof_l`|`_wcstof_l`|  
  
 Die `LC_NUMERIC`\-Kategorieeinstellung des aktuellen Gebietsschemas bestimmt das Erkennen des Basiszeichens in `nptr`. Weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Funktionen ohne `_l`\-Suffix verwenden das aktuelle Gebietsschema; diejenigen ohne das Suffix sind beinahe identisch, verwenden jedoch stattdessen den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Wenn `endptr` nicht `NULL` ist, wird ein Zeiger auf das Zeichen, das die Überprüfung beendet hat, an dem Ort gespeichert, der auf `endptr` zeigt.  Wenn keine Konvertierung ausgeführt werden kann \(keine gültigen Ziffern gefunden oder ungültige Basis angegeben\), wird der Wert von `nptr` an dem Speicherort gespeichert, auf den von `endptr` gezeigt wird.  
  
 `strtof` erwartet, dass `nptr` auf eine Zeichenfolge der folgenden Form zeigt:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E`}\[`sign`\]`digits`\]  
  
 `whitespace` besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden; `sign` ist entweder Pluszeichen \(`+`\) oder Minuszeichen \(`–`\); and `digits` sind eine oder mehrere Dezimalstellen.  Wenn keine Ziffern vor dem Basiszeichen stehen, muss mindestens eine Ziffer nach dem Basiszeichen stehen.  Auf die Dezimalstellen kann ein Exponent folgen, der aus einem einführenden Buchstaben \(`d`, `D`, `e` oder `E`\) und einer optional Zahl mit Vorzeichen besteht.  Wenn weder ein Exponententeil noch ein Basiszeichen angezeigt wird, wird davon ausgegangen, dass ein Basiszeichen auf die letzte Ziffer in der Zeichenfolge folgt.  Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strtof`, `_strtof_l`|\<stdlib.h\>|  
|`wcstof`, `_wcstof_l`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strtof.c  
// This program uses strtof to convert a  
// string to a single-precision value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *string;  
   char *stopstring;  
   float x;  
  
   string = "3.14159This stopped it";  
   x = strtof(string, &stopstring);  
   printf("string = %s\n", string);  
   printf("   strtof = %f\n", x);  
   printf("   Stopped scan at: %s\n\n", stopstring);  
}  
```  
  
  **string \= 3.14159This stopped it**  
 **strtof \= 3.141590**  
 **Stopped scan at: This stopped it**   
## .NET Framework-Entsprechung  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)