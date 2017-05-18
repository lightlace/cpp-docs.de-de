---
title: asctime, _wasctime | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wasctime
- asctime
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
- _tasctime
- asctime
- _wasctime
dev_langs:
- C++
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 91f0ffd5b02f9e8bc34604683c6274ec0f2c28b3
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="asctime-wasctime"></a>asctime, _wasctime
Konvertieren Sie eine `tm`-Zeitstruktur in einer Zeichenfolge. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `timeptr`  
 Zeit-/Datumsstruktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `asctime` gibt einen Zeiger auf das Zeichenfolgeergebnis zurück; `_wasctime` gibt einen Zeiger auf das Breitzeichenfolge-Ergebnis zurück. Es gibt keinen Fehlerrückgabewert.  
  
## <a name="remarks"></a>Hinweise  
 Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
 Die `asctime`-Funktion konvertiert eine als Struktur gespeicherte Zeit in eine Zeichenfolge. Der `timeptr`-Wert wird normalerweise durch eine Forderung an `gmtime` oder `localtime` abgerufen. Diese geben beide wie in TIME.H definiert einen Zeiger auf eine `tm`-Struktur zurück.  
  
|timeptr.member|Wert|  
|--------------------|-----------|  
|`tm_hour`|Stunden seit Mitternacht (0-23)|  
|`tm_isdst`|Positiv bei Sommerzeit; 0 bei Winterzeit; negativ bei unbekannter Zeit. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit (DST, Daylight Saving Time) zu implementieren.|  
|`tm_mday`|Tag des Monats (1-31)|  
|`tm_min`|Minuten nach Stunde (0-59)|  
|`tm_mon`|Monat (0-11; Januar = 0)|  
|`tm_sec`|Sekunden nach Minute (0-59)|  
|`tm_wday`|Tag der Woche (0-6; Sonntag = 0)|  
|`tm_yday`|Tag des Jahres (0-365; 1. Januar = 0)|  
|`tm_year`|Jahr (aktuelles Jahr minus 1900)|  
  
 Die konvertierte Zeichenfolge wird auch gemäß den lokalen Zeitzoneneinstellungen angepasst. Informationen zur Konfiguration der Zeitzonen finden Sie unter den [time](../../c-runtime-library/reference/time-time32-time64.md), [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)-Funktionen. Informationen zur Definition der Zeitzonenumgebung und globalen Variablen finden Sie unter der [_tzset](../../c-runtime-library/reference/tzset.md)-Funktion.  
  
 Das von `asctime` erstellte Zeichenfolgeergebnis enthält genau 26 Zeichen und sieht so aus: `Wed Jan 02 02:03:55 1980\n\0`. Eine 24-Stunden-Uhr wird verwendet. Alle Felder haben eine feste Breite. Die Zeilenwechsel- und Nullzeichen nehmen die letzten beiden Stellen der Zeichenfolge ein. `asctime` verwendet einen einzelnen, statisch zugeordneten Puffer, um die Rückgabezeichenfolge zu halten. Jeder Aufruf dieser Funktion zerstört das Ergebnis des vorherigen Aufrufs.  
  
 `_wasctime` ist eine Breitzeichenversion von `asctime`. `_wasctime` und `asctime` verhalten sich andernfalls identisch.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `timeptr` ein NULL-Zeiger ist oder es Werte außerhalb des Bereichs enthält, wird der ungültige Parameterhandler ausgelöst, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion `NULL` zurück und setzt `errno` auf `EINVAL`.  
  
### <a name="generic-text-routine-mapping"></a>Routinemäßige Allgemeintext-Zuordnung  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`asctime`|\<time.h>|  
|`_wasctime`|\<time.h> oder \<wchar.h>|  
  
## <a name="example"></a>Beispiel  
 Dieses Programm platziert die Systemzeit in ein längeres, ganzzahliges `aclock`, übersetzt sie in die Struktur `newtime` und konvertiert sie dann mithilfe der `asctime`-Funktion in eine Zeichenfolgeform für die Ausgabe.  
  
```  
// crt_asctime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
    struct tm   *newTime;  
    time_t      szClock;  
  
    // Get time in seconds  
    time( &szClock );  
  
    // Convert time to struct tm form   
    newTime = localtime( &szClock );  
  
    // Print local time as a string.  
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996  
    // Note: asctime is deprecated; consider using asctime_s instead  
}  
```  
  
```Output  
Current date and time: Sun Feb 03 11:38:58 2002  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)
