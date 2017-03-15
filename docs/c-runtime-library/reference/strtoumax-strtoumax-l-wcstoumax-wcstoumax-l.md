---
title: "strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcstoumax_l"
  - "_strtoumax_l"
  - "wcstoumax"
  - "strtoumax"
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
  - "wcstoumax"
  - "_tcstoumax"
  - "_strtoumax_l"
  - "_wcstoumax_l"
  - "_tcstoumax_l"
  - "strtoumax"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtoumax_l-Funktion"
  - "_wcstoumax_l-Funktion"
  - "Konvertierungsfunktionen"
  - "strtoumax-Funktion"
  - "wcstoumax-Funktion"
ms.assetid: 566769f9-495b-4508-b9c6-02217a578897
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert Zeichenfolgen in einen ganzzahligen Wert des größten unterstützten ganzzahligen Typs ohne Vorzeichen.  
  
## Syntax  
  
```  
uintmax_t strtoumax(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
uintmax_t _strtoumax_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
uintmax_t wcstoumax(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
uintmax_t _wcstoumax_l(  
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
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 `strtoumax` gibt den konvertierten Wert zurück, sofern vorhanden, oder `UINTMAX_MAX` im Falle eines Überlaufs.  `strtoumax` gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann.  `wcstoumax` gibt Werte analog zu `strtoumax` zurück.  Für beide Funktionen wird `errno` auf `ERANGE` festgelegt, wenn ein Überlauf oder Unterlauf auftritt.  
  
 Weitere Informationen zu Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Jede dieser Funktionen konvertiert die Eingabezeichenfolge `nptr` in einen ganzzahligen `uintmax_t`\-Wert.  
  
 `strtoumax` stoppt das Lesen der `nptr`\-Zeichenfolge beim ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dies ist möglicherweise das abschließende NULL\-Zeichen, kann aber auch das erste numerische Zeichen sein, das größer oder gleich `base` ist.  Die `LC_NUMERIC`\-Kategorieneinstellung des Gebietsschemas bestimmt das Erkennen des Basiszeichens in `nptr`.  Weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  `strtoumax` und`wcstoumax` verwenden das aktuelle Gebietsschema; `_strtoumax_l` und`_wcstoumax_l` sind identisch, verwenden allerdings das übergebene Gebietsschema.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Wenn `endptr` nicht `NULL` ist, wird ein Zeiger auf das Zeichen, das die Überprüfung beendet hat, an dem Ort gespeichert, der auf `endptr` zeigt.  Wenn keine Konvertierung ausgeführt werden kann \(keine gültigen Ziffern gefunden oder ungültige Basis angegeben\), wird der Wert von `nptr` an dem Speicherort gespeichert, auf den von `endptr` gezeigt wird.  
  
 Die Breitzeichenversion von `strtoumax` ist `wcstoumax`. Das dazugehörige `nptr`\-Argument ist eine Breitzeichenfolge.  Ansonsten verhalten sich diese Funktionen identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcstoumax`|`strtoumax`|`strtoumax`|`wcstoumax`|  
|`_tcstoumax_l`|`strtoumax_l`|`_strtoumax_l`|`_wcstoumax_l`|  
  
 `strtoumax` erwartet, dass `nptr` auf eine Zeichenfolge der folgenden Form zeigt:  
  
 \[`whitespace`\] \[{`+` &#124; `–`}\] \[`0` \[{ `x` &#124; `X` }\]\] \[`digits` &#124; \[`letters`\]\]  
  
 `whitespace` besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden; `digits` sind mindestens eine Dezimalstelle; `letters` sind mindestens ein Buchstabe von "a" bis "z" \(oder "A" bis "Z "\).  Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung.  Wenn `base` zwischen 2 und 36 liegt, wird dieser Wert als Basis der Zahl verwendet.  Wenn `base` 0 ist, werden die ersten Zeichen der Zeichenfolge verwendet, auf die von `nptr` gezeigt wird, um die Basis festzulegen.  Wenn das erste Zeichen "0 " und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als oktale ganze Zahl interpretiert.  Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert.  Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert.  Die Buchstaben "a" bis "z" \(bzw. "A" bis "Z"\) werden den Werten 10 bis 35 zugewiesen. Nur Buchstaben, deren zugewiesene Werte kleiner als `base` sind, sind zulässig.  Das erste Zeichen außerhalb des Bereichs der Basis beendet die Überprüfung.  Wenn beispielsweise `base` 0 und das erste überprüfte Zeichen "0" ist, wird eine ganze Oktalzahl angenommen und ein "8"\- oder "9"\-Zeichen beendet die Überprüfung.  `strtoumax` lässt ein Pluszeichen \(`+`\) oder ein Minuszeichen \(`–`\) als Präfix zu. Ein führendes Minuszeichen gibt an, dass der Rückgabewert das Zweierkomplement des absoluten Werts der konvertierten Zeichenfolge ist.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strtoumax`|\<stdlib.h\>|  
|`wcstoumax`|\<stdlib.h\> oder \<wchar.h\>|  
|`_strtoumax_l`|\<stdlib.h\>|  
|`_wcstoumax_l`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Betrachten Sie das Beispiel für [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
## .NET Framework-Entsprechung  
 [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoimax, \_strtoimax\_l, wcstoimax, \_wcstoimax\_l](../../c-runtime-library/reference/strtoimax-strtoimax-l-wcstoimax-wcstoimax-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoll, \_strtoll\_l, wcstoll, \_wcstoll\_l](../../c-runtime-library/reference/strtoll-strtoll-l-wcstoll-wcstoll-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)