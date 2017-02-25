---
title: "strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstoimax"
  - "_wcstoimax_l"
  - "_strtoimax_l"
  - "strtoimax"
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
  - "wcstoimax"
  - "_tcstoimax"
  - "strtoimax"
  - "_wcstoimax_l"
  - "_strtoimax_l"
  - "_tcstoimax_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoimax_l-Funktion"
  - "_wcstoimax_l-Funktion"
  - "Konvertierungsfunktionen"
  - "strtoimax-Funktion"
  - "wcstoimax-Funktion"
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge in einen ganzzahligen Wert des größten unterstützten ganzzahligen Typs mit Vorzeichen.  
  
## Syntax  
  
```  
intmax_t strtoimax(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
intmax_t wcstoimax(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
intmax_t _strtoimax_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
intmax_t _wcstoimax_l(  
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
 Zeiger auf das Zeichen, das die Überprüfung stoppt.  
  
 `base`  
 Zu verwendende Zahlenbasis.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 `strtoimax` gibt den Wert zurück, der in der Zeichenfolge `nptr` dargestellt wird, es sei denn, die Darstellung erzeugt einen Überlauf. In diesem Fall wird `INTMAX_MAX` oder `INTMAX_MIN` zurückgegeben und `errno` auf `ERANGE` festgelegt.  Die Funktion gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann.  `wcstoimax` gibt Werte analog zu `strtoimax` zurück.  
  
 `INTMAX_MAX` und `INTMAX_MIN` werden in stdint.h definiert.  
  
 Wenn `nptr``NULL` ist, oder `base` nicht NULL und entweder weniger als 2 oder größer als 36 ist, wird `errno` auf `EINVAL` festgelegt.  
  
 Weitere Informationen zu Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `strtoimax`\-Funktion konvertiert `nptr` in `intmax_t`.  Die Breitzeichenversion von `strtoimax` ist `wcstoimax`. Das dazugehörige `nptr`\-Argument ist eine Breitzeichenfolge.  Ansonsten verhalten sich diese Funktionen identisch.  Beide Funktionen beenden das Lesen der `nptr`\-Zeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dies ist möglicherweise das abschließende NULL\-Zeichen, kann aber auch das erste numerische Zeichen sein, das größer oder gleich `base` ist.  
  
 Die `LC_NUMERIC`\-Kategorieeinstellung des Gebietsschemas bestimmt das Erkennen des Basiszeichens in `nptr`. Weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema. `_strtoimax_l` und `_wcstoimax_l` sind mit den entsprechenden Funktionen ohne das `_l`\-Suffix nahezu identisch haben, verwenden jedoch stattdessen das übergebene Gebietsschema.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Wenn `endptr` nicht `NULL` ist, wird ein Zeiger auf das Zeichen, das die Überprüfung beendet hat, an dem Ort gespeichert, der auf `endptr` zeigt.  Wenn keine Konvertierung ausgeführt werden kann \(keine gültigen Ziffern gefunden oder ungültige Basis angegeben\), wird der Wert von `nptr` an dem Speicherort gespeichert, auf den von `endptr` gezeigt wird.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcstoimax`|`strtoimax`|`strtoimax`|`wcstoimax`|  
|`_tcstoimax_l`|`strtoimax_l`|`_strtoimax_l`|`_wcstoimax_l`|  
  
 `strtoimax` erwartet, dass `nptr` auf eine Zeichenfolge der folgenden Form zeigt:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits` &#124; `letters`\]  
  
 `whitespace` besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden; `digits` sind mindestens eine Dezimalstelle; `letters` sind mindestens ein Buchstabe von "a" bis "z" \(oder "A" bis "Z "\).  Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung.  Wenn `base` zwischen 2 und 36 liegt, wird dieser Wert als Basis der Zahl verwendet.  Wenn `base` 0 ist, werden die ersten Zeichen der Zeichenfolge, auf die durch `nptr` gezeigt wird, zur Bestimmung der Basis verwendet.  Wenn das erste Zeichen "0 " und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als oktale ganze Zahl interpretiert.  Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert.  Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert.  Die Buchstaben "a" bis "z" \(bzw. "A" bis "Z"\) werden den Werten 10 bis 35 zugewiesen. Nur Buchstaben, deren zugewiesene Werte kleiner als `base` sind, sind zulässig.  Das erste Zeichen außerhalb des Bereichs der Basis beendet die Überprüfung.  Wenn beispielsweise `base` 0 und das erste überprüfte Zeichen "0" ist, wird eine ganze Oktalzahl angenommen und ein "8"\- oder "9"\-Zeichen beendet die Überprüfung.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strtoimax`, `_strtoimax_l`, `wcstoimax`, `_wcstoimax_l`|\<inttypes.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoumax, \_strtoumax\_l, wcstoumax, \_wcstoumax\_l](../../c-runtime-library/reference/strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)