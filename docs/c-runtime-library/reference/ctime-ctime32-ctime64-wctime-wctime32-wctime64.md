---
title: ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
dev_langs: C++
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97c6f5f4c827ca315eb1de36ee8d4f19d94214bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
Konvertieren Sie einen Zeitwert in eine Zeichenfolge, und passen Sie sie an die Zeitzoneneinstellungen an. Sicherere Versionen dieser Funktionen sind verfügbar. Sie finden sie unter [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `timer`  
 Zeiger auf die gespeicherte Zeit  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Zeichenfolgenergebnis `NULL` wird in folgenden Fällen zurückgegeben:  
  
-   `time` ein Datum vor dem 1. Januar 1970 um Mitternacht (koordinierte Weltzeit, UTC) darstellt.  
  
-   Wenn Sie `_ctime32` oder `_wctime32` verwenden, und `time` ein Datum nach dem 18. Januar 2038, 23:59:59 Uhr (koordinierte Weltzeit, UTC) darstellt.  
  
-   Wenn Sie `_ctime64` oder `_wctime64` verwenden, und `time` ein Datum nach dem 31. Dezember 3000, 23:59:59 Uhr (koordinierte Weltzeit, UTC) darstellt.  
  
 `ctime` ist eine Inlinefunktion, die `_ctime64` auswertet, und `time_t` entspricht `__time64_t`. Wenn Sie den Compiler zwingen müssen, `time_t` als das alte 32-Bit-`time_t` zu interpretieren, können Sie `_USE_32BIT_TIME_T` definieren. Dadurch wird `ctime` mit `_ctime32` ausgewertet. Dies ist nicht zu empfehlen, weil Ihre Anwendung nach dem 18. Januar 2038 fehlschlagen kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Die `ctime`-Funktion konvertiert einen als [time_t](../../c-runtime-library/standard-types.md)-Wert gespeicherten Zeitwert in eine Zeichenfolge. Der `timer`-Wert ergibt sich normalerweise aus einem Aufruf von [time](../../c-runtime-library/reference/time-time32-time64.md) und gibt die Anzahl der Sekunden zurück, die seit Mitternacht (00:00:00 Uhr, koordinierte Weltzeit, UTC) am 1. Januar 1970 verstrichen sind. Der Rückgabewert der Zeichenfolge enthält genau 26 Zeichen und sieht so aus:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Eine 24-Stunden-Uhr wird verwendet. Alle Felder haben eine feste Breite. Das Zeichen für neue Zeile ('\n') und das Nullzeichen ('\0') nehmen die letzten beiden Stellen der Zeichenfolge ein.  
  
 Die konvertierte Zeichenfolge wird auch gemäß den lokalen Zeitzoneneinstellungen angepasst. Informationen zur Konfiguration der lokalen Zeit finden Sie unter den `time`, [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)-Funktionen. Einzelheiten zur Definition der Zeitzonenumgebung und der globalen Variablen finden Sie unter der [_tzset](../../c-runtime-library/reference/tzset.md)-Funktion.  
  
 Ein Aufruf von `ctime` ändert die einzelnen statisch zugewiesenen Puffer, die von der `gmtime`- und der `localtime`-Funktion verwendet werden. Bei jedem Aufruf dieser Routinen wird das Ergebnis des vorherigen Aufrufs zerstört. `ctime` teilt einen statischen Puffer mit der `asctime`-Funktion. Daher zerstört ein Aufruf von `ctime` die Ergebnisse jedes vorherigen Aufrufs von `asctime`, `localtime` oder `gmtime`.  
  
 `_wctime` und `_wctime64` sind die Breitzeichenversion von `ctime` und `_ctime64` und geben einen Zeiger auf die Breitzeichen-Zeichenfolge zurück. Andernfalls verhalten sich `_ctime64`, `_wctime` und `_wctime64` identisch zu `ctime`.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `timer` ein ungültiger NULL-Zeiger oder der Zeitwert negativ ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und setzt `errno` auf `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`ctime`|\<time.h>|  
|`_ctime32`|\<time.h>|  
|`_ctime64`|\<time.h>|  
|`_wctime`|\<time.h> oder \<wchar.h>|  
|`_wctime32`|\<time.h> oder \<wchar.h>|  
|`_wctime64`|\<time.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
The time is Wed Feb 13 16:04:43 2002  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)