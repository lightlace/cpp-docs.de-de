---
title: strtol, wcstol, _strtol_l, _wcstol_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
dev_langs: C++
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 08a476172291c52865fe2abb9fb872e388078ac5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strtol-wcstol-strtoll-wcstoll"></a>strtol, wcstol, _strtol_l, _wcstol_l
Konvertiert Zeichenfolgen in einen langen ganzzahligen Wert.  
  
## <a name="syntax"></a>Syntax  
  
```  
long strtol(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
long wcstol(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
long _strtol_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
long _wcstol_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `nptr`  
 Zu konvertierende mit NULL endende Zeichenfolge.  
  
 `endptr`  
 Zeiger auf ein Zeichen, mit dem die Überprüfung beendet wird.  
  
 `base`  
 Zu verwendende Zahlenbasis.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 `strtol` gibt den in der Zeichenfolge `nptr` dargestellten Wert zurück, es sei denn, die Darstellung würde einen Überlauf verursachen. In diesem Fall wird `LONG_MAX` oder `LONG_MIN` zurückgegeben. `strtol` gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann. `wcstol` gibt Werte analog zu `strtol` zurück. Für beide Funktionen wird `errno` auf `ERANGE` festgelegt, wenn ein Überlauf oder Unterlauf auftritt.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `strtol`-Funktion konvertiert `nptr` in `long`. `strtol` stoppt das Lesen der `nptr`-Zeichenfolge beim ersten Zeichen, das nicht als Teil einer Zahl erkannt wird. Dies ist möglicherweise das abschließende Nullzeichen, kann aber auch das erste numerische Zeichen sein, dass größer oder gleich `base` ist.  
  
 `wcstol` ist eine Breitzeichenversion von `strtol`. Das dazugehörige `nptr`-Argument ist eine Breitzeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstol`|`strtol`|`strtol`|`wcstol`|  
|`_tcstol_l`|`_strtol_l`|`_strtol_l`|`_wcstol_l`|  
  
 Die `LC_NUMERIC`-Kategorieeinstellung des aktuellen Gebietsschemas bestimmt die Erkennung des Basiszeichens in `nptr`*.* Weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Funktionen ohne das `_l`-Suffix verwenden das aktuelle Gebietsschema. `_strtol_l` und `_wcstol_l` sind mit den entsprechenden Funktionen ohne das `_l`-Suffix identisch, außer dass sie stattdessen das übergebene Gebietsschema verwenden. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Wenn `endptr` nicht `NULL` ist, wird ein Zeiger auf das Zeichen, das die Überprüfung beendet hat, an dem Ort gespeichert, auf den durch `endptr` gezeigt wird. Wenn keine Konvertierung ausgeführt werden kann (keine gültigen Ziffern gefunden oder ungültige Basis angegeben), wird der Wert von `nptr` an dem Speicherort gespeichert, auf den durch `endptr` gezeigt wird.  
  
 `strtol` erwartet, dass `nptr` auf eine Zeichenfolge der folgenden Form zeigt:  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 `whitespace` besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden. `digits` sind eine oder mehrere Dezimalstellen. Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung. Wenn `base` zwischen 2 und 36 liegt, wird dieser Wert als Basis der Zahl verwendet. Wenn `base` 0 ist, werden die ersten Zeichen der Zeichenfolge, auf die durch `nptr` gezeigt wird, zur Bestimmung der Basis verwendet. Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als ganze Oktalzahl interpretiert. Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert. Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert. Die Buchstaben "a" bis "z" (bzw. "A" bis "Z") werden den Werten 10 bis 35 zugewiesen. Nur Buchstaben, deren zugewiesene Werte kleiner als `base` sind, sind zulässig. Das erste Zeichen außerhalb des Bereichs der Basis beendet die Überprüfung. Wenn beispielsweise `base` 0 und das erste überprüfte Zeichen "0" ist, wird eine ganze Oktalzahl angenommen und das Zeichen "8" oder "9" beendet die Überprüfung.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`strtol`|\<stdlib.h>|  
|`wcstol`|\<stdlib.h> oder \<wchar.h>|  
|`_strtol_l`|\<stdlib.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)