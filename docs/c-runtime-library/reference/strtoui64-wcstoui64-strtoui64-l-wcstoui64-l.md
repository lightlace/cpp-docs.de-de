---
title: "_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strtoui64"
  - "_strtoui64_l"
  - "_wcstoui64"
  - "_wcstoui64_l"
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
  - "_wcstoui64_l"
  - "strtoui64_l"
  - "wcstoui64"
  - "_wcstoui64"
  - "_strtoui64_l"
  - "strtoui64"
  - "_strtoui64"
  - "wcstoui64_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoui64-Funktion"
  - "_strtoui64_l-Funktion"
  - "_wcstoui64-Funktion"
  - "_wcstoui64_l-Funktion"
  - "Zeichenfolgenkonvertierung, in ganze Zahlen"
  - "strtoui64-Funktion"
  - "strtoui64_l-Funktion"
  - "wcstoui64-Funktion"
  - "wcstoui64_l-Funktion"
ms.assetid: 7fcb537e-4554-4ceb-a5b6-bc09244e72ef
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge in einen `__int64`\-Wert ohne Vorzeichen.  
  
## Syntax  
  
```  
unsigned __int64 _strtoui64(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned __int64 _wcstoui64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned __int64 _strtoui64_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned __int64 _wcstoui64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `nptr`  
 Zu konvertierende mit NULL endende Zeichenfolge.  
  
 `endptr`  
 Zeiger auf ein Zeichen, mit dem die Überprüfung beendet wird.  
  
 `base`  
 Zu verwendende Zahlenbasis.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 `_strtoui64` gibt den Wert zurück, der in der Zeichenfolge `nptr`, außer dargestellt wird, als Darstellung ein Überlauf verursacht, in diesem Fall die `_UI64_MAX` zurückgibt. \_`strtoui64` gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann.  
  
 `_UI64_MAX` wird in LIMITS.H. definiert.  
  
 Wenn `nptr``NULL` ist, oder `base` nicht NULL und entweder weniger als 2 oder größer als 36 ist, wird `errno` auf `EINVAL` festgelegt.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_strtoui64`\- Funktion konvertiert `nptr` in `unsigned` `__int64`.  `_wcstoui64` ist eine Breitzeichenversion von `_strtoui64`. Das dazugehörige `nptr`\-Argument ist eine Breitzeichenfolge.  Anderenfalls verhalten sich diese Funktionen identisch.  
  
 Beide Funktionen beenden das Lesen der `nptr`\-Zeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dies ist möglicherweise das abschließende Nullzeichen, kann aber auch das erste numerische Zeichen sein, dass größer oder gleich `base` ist.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcstoui64`|`_strtoui64`|`_strtoui64`|`_wstrtoui64`|  
|`_tcstoui64_l`|`_strtoui64_l`|`_strtoui64_l`|`_wstrtoui64_l`|  
  
 Die `LC_NUMERIC` \-Kategorieeinstellung des aktuellen Gebietsschemas bestimmt das Erkennen des Basiszeichens in `nptr`[.](../../c-runtime-library/reference/setlocale-wsetlocale.md) Weitere Informationen finden Sie unter setlocale.  Die Features ohne das \_l Suffix verwenden das aktuelle Gebietsschema; `_strtoui64_l`  und `_wcstoui64_l`  entsprechen den entsprechenden Funktionen ohne das Suffix `_l` identisch, allerdings verwenden das Gebietsschema, das ein\- stattdessen übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Wenn `endptr` nicht `NULL` ist, wird ein Zeiger auf das Zeichen, das die Überprüfung beendet hat, an dem Ort gespeichert, auf den durch `endptr` gezeigt wird.  Wenn keine Konvertierung ausgeführt werden kann \(keine gültigen Ziffern gefunden oder ungültige Basis angegeben\), wird der Wert von `nptr` an dem Speicherort gespeichert, auf den durch `endptr` gezeigt wird.  
  
 `_strtoui64`  erwartet, dass `nptr` auf eine Zeichenfolge der folgenden Form zeigt:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits`\]  
  
 `whitespace`  besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden. `digits`  sind eine oder mehrere Dezimalstellen.  Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung.  Wenn `base` zwischen 2 und 36 liegt, wird dieser Wert als Basis der Zahl verwendet.  Wenn `base` 0 ist, werden die ersten Zeichen der Zeichenfolge, auf die durch `nptr` gezeigt wird, zur Bestimmung der Basis verwendet.  Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als ganze Oktalzahl interpretiert.  Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert.  Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert.  Die Buchstaben "a" bis "z" \(bzw. "A" bis "Z"\) werden den Werten 10 bis 35 zugewiesen. Nur Buchstaben, deren zugewiesene Werte kleiner als `base` sind, sind zulässig.  Das erste Zeichen außerhalb des Bereichs der Basis beendet die Überprüfung.  Wenn beispielsweise `base` 0 und das erste überprüfte Zeichen "0" ist, wird eine ganze Oktalzahl angenommen und das Zeichen "8" oder "9" beendet die Überprüfung.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_strtoui64`|\<stdlib.h\>|  
|`_wcstoui64`|\<stdlib.h\> oder \<wchar.h\>|  
|`_strtoui64_l`|\<stdlib.h\>|  
|`_wcstoui64_l`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_strtoui64.c  
#include <stdio.h>  
  
unsigned __int64 atoui64(const char *szUnsignedInt) {  
   return _strtoui64(szUnsignedInt, NULL, 10);  
}  
  
int main() {  
   unsigned __int64 u = atoui64("18446744073709551615");  
   printf( "u = %I64u\n", u );  
}  
```  
  
  **u \= 18446744073709551615**   
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)