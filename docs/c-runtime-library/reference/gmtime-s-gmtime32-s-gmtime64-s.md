---
title: gmtime_s, _gmtime32_s, _gmtime64_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
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
- _gmtime_s
- gmtime64_s
- gmtime32_s
- _gmtime64_s
- gmtime_s
- _gmtime32_s
dev_langs:
- C++
helpviewer_keywords:
- gmtime_s function
- gmtime32_s function
- time functions
- gmtime64_s function
- _gmtime64_s function
- time structure conversion
- _gmtime_s function
- _gmtime32_s function
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92a840d608a892a117b6552e0b81c8dd3b6fcdb0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="gmtimes-gmtime32s-gmtime64s"></a>gmtime_s, _gmtime32_s, _gmtime64_s
Konvertiert einen Zeitwert in eine Struktur. Dies sind Versionen von [_gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) mit Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t gmtime_s(  
   struct tm* _tm,  
   const __time_t* time  
);  
errno_t _gmtime32_s(  
   struct tm* _tm,  
   const __time32_t* time  
);  
errno_t _gmtime64_s(  
   struct tm* _tm,  
   const __time64_t* time   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `_tm`  
 Zeiger auf eine `tm`-Struktur. Die Felder der zurückgegebenen Struktur enthalten den ausgewerteten Wert des `timer`-Arguments im UTC-Format. Die Angabe erfolgt nicht in Ortszeit.  
  
 `time`  
 Zeiger auf die gespeicherte Zeit Die Zeit wird in Sekunden dargestellt, die seit dem 1. Januar 1970, Mitternacht (00:00: 00), verstrichen sind. Die Anzeige erfolgt im UTC-Format.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. Eine Liste dieser Fehler finden Sie unter [errno](../../c-runtime-library/errno-constants.md).  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`_tm`|`time`|Zurück|Wert in `_tm`.|  
|-----------|------------|------------|--------------------|  
|`NULL`|any|`EINVAL`|Nicht geändert.|  
|Nicht `NULL` (zeigt gültigen Speicher an)|`NULL`|`EINVAL`|Alle Felder auf -1 festgelegt.|  
|Nicht `NULL`|< 0|`EINVAL`|Alle Felder auf -1 festgelegt.|  
  
 Im Fall der ersten zwei Fehlerbedingungen, wird der ungültige Parameterhandler aufgerufen, wie es unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_gmtime32_s`-Funktion gliedert den `time`-Wert und speichert diesen in eine Struktur vom Typ `tm`, die in Time.h. definiert ist. Die Adresse dieser Struktur wird in `_tm` übergeben. Der Wert von `time` wird normalerweise durch einen Aufruf der `time`-Funktion abgerufen.  
  
> [!NOTE]
>  Die Zielumgebung soll versuchen, zu bestimmen, ob die Sommerzeit wirksam ist. Die C-Laufzeitbibliothek wendet die Regeln der Vereinigten Staaten an, um die Berechnung der Sommerzeit zu implementieren.  
  
 Jedes Strukturfeld ist vom Typ `int`, wie in der folgenden Tabelle dargestellt wird.  
  
 `tm_sec`  
 Sekunden nach Minute (0 - 59).  
  
 `tm_min`  
 Minuten nach Stunde (0 - 59).  
  
 `tm_hour`  
 Stunden seit Mitternacht (0 - 23).  
  
 `tm_mday`  
 Tag des Monats (1-31).  
  
 `tm_mon`  
 Monat (0 - 11; Januar = 0).  
  
 `tm_year`  
 Jahr (aktuelles Jahr minus 1900).  
  
 `tm_wday`  
 Tag der Woche (0 - 6; Sonntag = 0).  
  
 `tm_yday`  
 Tag des Jahres (0 - 365; 1. Januar = 0).  
  
 `tm_isdst`  
 Für `gmtime` immer 0.  
  
 `_gmtime64_s`, das die `__time64_t`-Struktur verwendet, erlaubt das Ausdrücken von Daten über den 31. Dezember 3000, 23:59:59 UTC hinaus, während `gmtime32_s` nur Datumsangaben bis zum 18. Januar 2038, 23:59:59 UTC, darstellt. Der 1. Januar 1970 (Mitternacht) ist der untere Datumsbereich für diese beiden Funktionen.  
  
 `gmtime_s` ist eine Inlinefunktion, die `_gmtime64_s` auswertet, und `time_t` entspricht `__time64_t`. Wenn Sie den Compiler zwingen müssen, `time_t` als das alte 32-Bit- `time_t`zu interpretieren, definieren Sie `_USE_32BIT_TIME_T`. Dadurch wird `gmtime_s` in `_gmtime32_s` eingebunden. Dies ist nicht zu empfehlen, weil bei Ihrer Anwendung nach dem 18. Januar 2038 ein Fehler auftreten kann. Die Verwendung dieses Makros ist auf 64-Bit-Plattformen nicht zulässig.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`gmtime_s`|\<time.h>|  
|`_gmtime32_s`|\<time.h>|  
|`_gmtime64_s`|\<time.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_gmtime64_s.c  
// This program uses _gmtime64_s to convert a 64-bit  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime_s to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm newtime;  
   __int64 ltime;  
   char buf[26];  
   errno_t err;  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:   
   err = _gmtime64_s( &newtime, &ltime );  
   if (err)  
   {  
      printf("Invalid Argument to _gmtime64_s.");  
   }  
  
   // Convert to an ASCII representation   
   err = asctime_s(buf, 26, &newtime);  
   if (err)  
   {  
      printf("Invalid Argument to asctime_s.");  
   }  
  
   printf( "Coordinated universal time is %s\n",   
           buf );  
}  
```  
  
```Output  
Coordinated universal time is Fri Apr 25 20:12:33 2003  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)