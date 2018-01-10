---
title: strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsftime
- strftime
- wcsftime
dev_langs: C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 785ad16e8f86f74252c4391044d2def96091fe61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l
Formatieren einer Zeitzeichenfolge  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `strDest`  
 Ausgabezeichenfolge.  
  
 `maxsize`  
 Größe des `strDest`-Puffers in Zeichen (`char` oder `wchart_t`).  
  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `timeptr`  
 `tm`-Datenstruktur.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 `strftime` gibt die Anzahl der in `strDest` platzierten Daten zurück, und `wcsftime` gibt die entsprechende Anzahl von Breitzeichen zurück.  
  
 Wenn die Gesamtzahl der Zeichen, einschließlich des abschließende NULL-Zeichens, größer als `maxsize` ist, geben `strftime` und `wcsftime` 0 zurück, und der Inhalt von `strDest` ist unbestimmt.  
  
 Die Anzahl von Zeichen in `strDest` ist gleich der Anzahl von Literalzeichen in `format` sowie aller Zeichen, die `format` möglicherweise über Formatierungscodes hinzugefügt werden. Das abschließende NULL-Zeichen einer Zeichenfolge wird nicht im Rückgabewert berücksichtigt.  
  
## <a name="remarks"></a>Hinweise  
 Die `strftime` und `wcsftime` Formatieren der `tm` Zeitwert in `timeptr` gemäß den angegebenen `format` Argument und speichern das Ergebnis in den Puffer `strDest`. Höchstens `maxsize` Zeichen werden in die Zeichenfolge gestellt. Eine Beschreibung der Felder in der `timeptr`-Struktur finden Sie unter [asctime](../../c-runtime-library/reference/asctime-wasctime.md). `wcsftime` ist die Breitzeichenentsprechung von `strftime`; ihr Zeichenfolgenargument zeigt auf eine Breitzeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.  
  
> [!NOTE]
>  In Versionen vor Visual C++ 2005 hat der `format`-Parameter von `wcsftime` laut der Dokumentation den Datentypparameter `const wchar_t *`, aber die tatsächliche Implementierung des `format`-Datentyps war `const char *`. Die Implementierung der `format` -Datentyp wurde aktualisiert, um die vorherige und aktuelle-Dokumentation, d. h. widerspiegeln `const wchar_t *`.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `strDest`, `format`, oder `timeptr` ein null-Zeiger ist oder wenn die `tm` Datenstruktur adressiert werden, indem `timeptr` ist ungültig (z. B., wenn er außerhalb des gültigen Bereichswerte enthält, für das Datum oder Uhrzeit), oder wenn die `format` Zeichenfolge enthält eine ungültige Formatierungscode Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion 0 zurück und stellt `errno` auf `EINVAL` ein.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 Das `format`-Argument besteht aus mindestens einem Code; wie in `printf` ist den Formatierungscodes ein Prozentzeichen (`%`) vorangestellt. Zeichen, die nicht mit beginnen `%` beim Übertragungsvorgang kopiert werden unverändert an den `strDest`. Die `LC_TIME`-Kategorie des aktuellen Gebietsschemas wirkt sich auf die Ausgabeformatierung von `strftime` aus. (Weitere Informationen zu `LC_TIME` finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).) Die Funktion ohne das Suffix `_l` verwenden das aktuelle Gebietsschema. Die Versionen dieser Funktionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Die Formatierungscodes für `strftime` sind unten aufgeführt:  
  
 `%a`  
 Abgekürzte Wochentagbezeichnung  
  
 `%A`  
 Vollständige Wochentagbezeichnung  
  
 `%b`  
 Abgekürzte Monatsbezeichnung  
  
 `%B`  
 Vollständige Monatsbezeichnung  
  
 `%c`  
 Für das Gebietsschema geeignete Darstellung von Datum und Uhrzeit  
  
 `%d`  
 Tag des Monats wird als Dezimalzahl (01-31)  
  
 `%H`  
 Stundenangabe im 24-Stunden-Format (00 - 23)  
  
 `%I`  
 Stundenangabe im 12-Stunden-Format (01 bis 12)  
  
 `%j`  
 Tag des Jahres wird als Dezimalzahl (001-366)  
  
 `%m`  
 Monatsangabe als Dezimalzahl (01 bis 12)  
  
 `%M`  
 Minutenangabe als Dezimalzahl (00 - 59)  
  
 `%p`  
 A.M./P.M.-Kennung des aktuellen Gebietsschemas Indikator für 12-Stunden-Uhr  
  
 `%S`  
 Sekundenangabe als Dezimalzahl (00 - 59)  
  
 `%U`  
 Woche des Jahres wird als Dezimalzahl, wobei Sonntag den ersten Tag der Woche (00 - 53)  
  
 `%w`  
 Angabe des Wochentags als Dezimalzahl (0 - 6; Sonntag ist 0)  
  
 `%W`  
 Woche des Jahres wird als Dezimalzahl, wobei Montag den ersten Tag der Woche (00 - 53)  
  
 `%x`  
 Datumsdarstellung für das aktuelle Gebietsschema  
  
 `%X`  
 Uhrzeitdarstellung für das aktuelle Gebietsschema  
  
 `%y`  
 Jahresangabe ohne Jahrhundert als Dezimalzahl (00 - 99)  
  
 `%Y`  
 Jahresangabe mit Jahrhundert als Dezimalzahl  
  
 `%z, %Z`  
 Name oder Abkürzung der Zeitzone, abhängig von den Registrierungseinstellungen; keine Zeichen, wenn die Zeitzone unbekannt ist  
  
 `%%`  
 Prozentzeichen (%)  
  
 Wie in der `printf`-Funktion, wird das `#`-Flag möglicherweise dem Formatierungscode vorangestellt. In diesem Fall wird die Bedeutung des Formatcodes wie folgt geändert.  
  
|Formatcode|Bedeutung|  
|-----------------|-------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|`#`-Flag wird ignoriert.|  
|`%#c`|Für das Gebietsschema geeignete lange Darstellung von Datum und Uhrzeit. Beispiel: „Dienstag, 14. März 1995, 12:41:29“.|  
|`%#x`|Für das Gebietsschema geeignete lange Darstellung des Datums. Beispiel: „Dienstag, 14. März 1995“.|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|Entfernen Sie die führende Nullen (sofern vorhanden).|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`strftime`|\<time.h>|  
|`wcsftime`|\<time.h> oder \<wchar.h>|  
|`_strftime_l`|\<time.h>|  
|`_wcsftime_l`|\<time.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)