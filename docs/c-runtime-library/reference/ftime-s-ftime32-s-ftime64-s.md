---
title: _ftime_s, _ftime32_s, _ftime64_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
- _ftime_s
- _ftime64_s
- ftime_s
- _ftime32_s
- ftime32_s
- ftime64_s
dev_langs:
- C++
helpviewer_keywords:
- ftime32_s function
- ftime_s function
- _ftime64_s function
- current time
- ftime64_s function
- time, getting current
- _ftime_s function
- _ftime32_s function
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: baf4371e90dfe06a4896c33937f578a2483475d3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="ftimes-ftime32s-ftime64s"></a>_ftime_s, _ftime32_s, _ftime64_s
Ruft die aktuelle Zeit ab Dies sind Versionen von [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) mit Sicherheitsverbesserungen, wie in [Sicherheitsfunktionen in der CRT beschrieben](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _ftime_s(   
   struct _timeb *timeptr   
);  
errno_t _ftime32_s(   
   struct __timeb32 *timeptr   
);  
errno_t _ftime64_s(   
   struct __timeb64 *timeptr   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `timeptr`  
 Zeiger auf eine `_timeb`, `__timeb32`, oder `__timeb64` Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler. Wenn `timeptr` `NULL` ist, wird `EINVAL` zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die `_ftime_s` Funktion ruft die aktuelle lokale Zeit ab und speichert ihn in der Struktur verweist `timeptr`. Die `_timeb`, `__timeb32`, und `__timeb64` Strukturen in SYS\Timeb.h definiert sind. Sie enthalten vier Felder, die in der folgenden Tabelle aufgeführt werden.  
  
 `dstflag`  
 Ein Wert ungleich null, wenn die Sommerzeit zurzeit für die lokale Zeitzone gültig ist. (Eine Erläuterung dazu, wie die Sommerzeit festgelegt wird, finden Sie unter [_tzset](../../c-runtime-library/reference/tzset.md).)  
  
 `millitm`  
 Sekundenbruchteile in Millisekunden  
  
 `time`  
 Die Zeit in Sekunden seit dem 1. Januar 1970, Mitternacht (00: 00: 00) im UTC-Format  
  
 `timezone`  
 Differenz in Minuten, westwärts zwischen UTC und der Ortszeit Der Wert `timezone` wird aus dem Wert der globalen Variablen `_timezone` festgelegt (siehe `_tzset`).  
  
 `_ftime64_s` verwendet die `__timeb64`-Struktur und ermöglicht es, Erstellungsdaten von Dateien bis 23:59:59 am 31. Dezember 3000 (UTC) anzugeben, während `_ftime32_s` nur Datumsangaben bis 23:59:59 am 18. Januar 2038 darstellt. Der 1. Januar 1970 (Mitternacht) ist der älteste mögliche Datumsbereich für all diese Funktionen.  
  
 `_ftime_s` entspricht `_ftime64_s`, und `_timeb` enthält einen 64-Bit-Uhrzeitwert. Das trifft zu, sofern `_USE_32BIT_TIME_T` nicht definiert wurde. In diesem Fall ist das alte Verhalten wirksam. `_ftime_s` verwendet einen 32-Bit-Uhrzeitwert, und `_timeb` enthält einen 32-Bit-Uhrzeitwert.  
  
 `_ftime_s` überprüft die eigenen Parameter. Wenn ein NULL-Zeiger als `timeptr` übergeben wird, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt die Funktion `errno` auf `EINVAL` fest.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_ftime_s`|\<sys/types.h> und \<sys/timeb.h>|  
|`_ftime32_s`|\<sys/types.h> und \<sys/timeb.h>|  
|`_ftime64_s`|\<sys/types.h> und \<sys/timeb.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_ftime64_s.c  
// This program uses _ftime64_s to obtain the current  
// time and then stores this time in timebuffer.  
  
#include <stdio.h>  
#include <sys/timeb.h>  
#include <time.h>  
  
int main( void )  
{  
   struct _timeb timebuffer;  
   char timeline[26];  
   errno_t err;  
   time_t time1;  
   unsigned short millitm1;  
   short timezone1;  
   short dstflag1;  
  
   _ftime64_s( &timebuffer );  
  
    time1 = timebuffer.time;  
    millitm1 = timebuffer.millitm;  
    timezone1 = timebuffer.timezone;  
    dstflag1 = timebuffer.dstflag;  
  
   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",   
   time1);  
   printf( "Milliseconds: %d\n", millitm1);  
   printf( "Minutes between UTC and local time: %d\n", timezone1);  
   printf( "Daylight savings time flag (1 means Daylight time is in "  
           "effect): %d\n", dstflag1);   
  
   err = ctime_s( timeline, 26, & ( timebuffer.time ) );  
   if (err)  
   {  
       printf("Invalid argument to ctime_s. ");  
   }  
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,  
           &timeline[20] );  
}  
```  
  
```Output  
Seconds since midnight, January 1, 1970 (UTC): 1051553334  
Milliseconds: 230  
Minutes between UTC and local time: 480  
Daylight savings time flag (1 means Daylight time is in effect): 1  
The time is Mon Apr 28 11:08:54.230 2003  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)