---
title: gmtime, _gmtime32, _gmtime64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: d6acd03622ffd309e394fc076c2922492ac2475b
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64
Konvertiert einen Zeitwert in eine Struktur. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
struct tm *gmtime(   
   const time_t *timer   
);  
struct tm *_gmtime32(   
   const __time32_t *timer   
);  
struct tm *_gmtime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `timer`  
 Zeiger auf die gespeicherte Zeit. Die Zeit wird in Sekunden dargestellt, die seit dem 1. Januar 1970, Mitternacht (00:00: 00), verstrichen sind. Die Anzeige erfolgt im UTC-Format.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Struktur des Typs [tm](../../c-runtime-library/standard-types.md). Die Felder der zurückgegebenen Struktur enthalten den ausgewerteten Wert des `timer`-Arguments im UTC-Format. Die Angabe erfolgt nicht in Ortszeit. Jedes dieser Strukturfelder ist wie folgt vom Typ `int`:  
  
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
  
 Sowohl die 32-Bit- als auch die 64-Bit-Versionen von `gmtime`, `mktime`, `mkgmtime` und `localtime` nutzen für die Konvertierung pro Thread eine gemeinsame `tm`-Struktur. Jeder Aufruf dieser Funktionen zerstört das Ergebnis des vorherigen Aufrufs. Wenn `timer` ein Datum vor Mitternacht (1. Januar 1970) darstellt, gibt `gmtime``NULL` zurück. Es gibt keine Fehlerrückgabe.  
  
 `_gmtime64`, das die `__time64_t`-Struktur verwendet, ermöglicht das Ausdrücken von Daten über den 31. Dezember 3000, 23:59:59 UTC hinaus, während `_gmtime32` nur Datumsangaben bis zum 18. Januar 2038, 23:59:59 UTC, darstellt. Der 1. Januar 1970 (Mitternacht) ist der untere Datumsbereich für beide Funktionen.  
  
 `gmtime` ist eine Inlinefunktion, die `_gmtime64` auswertet, und `time_t` entspricht `__time64_t`, sofern nicht, `_USE_32BIT_TIME_T` definiert ist. Wenn Sie den Compiler zwingen müssen, `time_t` das alte 32-Bit-`time_t` zu interpretieren, können Sie `_USE_32BIT_TIME_T` definieren. Dies führt jedoch dazu, dass `gmtime` in `_gmtime32` eingebunden wird und dass `time_t` als `__time32_t` definiert wird. Diese Aktion sollte nicht durchgeführt werden, da sie auf 64-Bit-Plattformen nicht zugelassen ist und die Anwendung auf jedem Fall nach dem 18. Januar 2038 fehlschlägt.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `timer` ein NULL-Zeiger oder der Zeitwert negativ ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und setzt `errno` auf `EINVAL`.  
  
## <a name="remarks"></a>Hinweise  
 Die `_gmtime32`-Funktion gliedert den `timer`-Wert und speichert diesen in eine statistisch zugeordnete Struktur vom Typ `tm`, die in TIME.H. definiert ist. Der Wert von `timer` wird in der Regel durch einen Aufruf der `time`-Funktion abgerufen.  
  
> [!NOTE]
>  In den meisten Fällen versucht die Zielumgebung zu bestimmen, ob die Sommerzeit wirksam ist. Die C-Laufzeitbibliothek geht davon aus, dass die Regeln der Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit (DST, Daylight Saving Time) angewendet werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`gmtime`|\<time.h>|  
|`_gmtime32`|\<time.h>|  
|`_gmtime64`|\<time.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_gmtime.c  
// compile with: /W3  
// This program uses _gmtime64 to convert a long-  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm *newtime;  
   __int64 ltime;  
   char buff[80];  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:  
   newtime = _gmtime64( &ltime ); // C4996  
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s  
   asctime_s( buff, sizeof(buff), newtime );  
   printf( "Coordinated universal time is %s\n", buff );  
}  
```  
  
```Output  
Coordinated universal time is Tue Feb 12 23:11:31 2002  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
