---
title: mktime, _mktime32, _mktime64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mktime32
- mktime
- _mktime64
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
- mktime
- _mktime64
dev_langs:
- C++
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee2673f98f219559fd42d192dd934c8fe3eaed8c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="mktime-mktime32-mktime64"></a>mktime, _mktime32, _mktime64
Konvertiert die Ortszeit in einen Kalenderwert.  
  
## <a name="syntax"></a>Syntax  
  
```  
time_t mktime(  
   struct tm *timeptr   
);  
__time32_t _mktime32(  
   struct tm *timeptr   
);  
__time64_t _mktime64(  
   struct tm *timeptr   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *timeptr*  
 Zeiger auf Zeitstruktur. Weitere Informationen finden Sie unter [asctime](../../c-runtime-library/reference/asctime-wasctime.md).  
  
## <a name="return-value"></a>Rückgabewert  
 `_mktime32` gibt die angegebene Kalenderzeit als einen Wert des Typs [time_t](../../c-runtime-library/standard-types.md) zurück. Wenn *Timeptr* auf ein Datum vor Mitternacht, 1. Januar 1970 verweist oder wenn die Kalenderzeit nicht dargestellt werden kann, `_mktime32` gibt-1 zurück, die in den Typ umgewandelt `time_t`. Bei Verwendung `_mktime32` und *Timeptr* Verweise ein Datum nach 23:59:59 am 18. Januar 2038 Coordinated Universal Time (UTC), es gibt-1 zurück, in den Typ umgewandelt `time_t`.  
  
 `_mktime64` Gibt den Typ umgewandelt-1 zurück, `__time64_t` Wenn *Timeptr* verweist auf ein Datum nach 23:59:59 am 31. Dezember 3000 UTC.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `mktime`, `_mktime32` und `_mktime64` konvertieren die angegebene Zeitstruktur (möglicherweise unvollständig), auf die durch *timeptr* verwiesen wird, in eine vollständig definierte Struktur mit normalisierten Werten. Anschließend konvertieren sie die Struktur in einen Kalenderzeitwert des Typs `time_t`. Die konvertierte Zeit hat dieselbe Codierung wie die Werte, die von der Funktion [Uhrzeit](../../c-runtime-library/reference/time-time32-time64.md) zurückgegeben wurden. Die ursprünglichen Werte der Komponenten `tm_wday` und `tm_yday` der Struktur *timeptr* werden ignoriert. Die ursprünglichen Werte der anderen Komponenten werden nicht auf ihre Normbereiche beschränkt.  
  
 `mktime` ist eine Inlinefunktion, die `_mktime64` entspricht, es sei denn, dass `_USE_32BIT_TIME_T` definiert ist. In diesem Fall entspricht sie `_mktime32`.  
  
 Nach einer Anpassung an die koordinierte Weltzeit (UTC) verarbeitet `_mktime32` Datumsangaben von Mitternacht (UTC) des 1. Januar 1970 bis 23:59:59 (UTC) des 18. Januar 2038. `_mktime64` behandelt Datumsangaben von Mitternacht, 1. Januar 1970 bis 23:59:59, 31. Dezember 3000. 	Aufgrund dieser Anpassung geben diese Funktionen möglicherweise -1 zurück (umgewandelt in `time_t`, `__time32_t` oder `__time64_t`), obwohl das von Ihnen angegebene Datum innerhalb des Bereichs liegt. Wenn Sie sich zum Beispiel im ägyptischen Kairo aufhalten, wo die Ortszeit zwei Stunden vor der UTC liegt, werden diese zwei Stunden zunächst von dem in *timeptr* angegebenen Datum abgezogen. Dadurch liegt das Datum nun möglicherweise außerhalb des zulässigen Bereichs.  
  
 Diese Funktionen können zum Überprüfen und Ausfüllen einer tm-Struktur verwendet werden. Bei Erfolg legen diese Funktionen ggf. die Werte aus `tm_wday` und `tm_yday` fest. Die anderen Komponenten werden so festgelegt, dass die angegebene Kalenderzeit dargestellt wird, jedoch mit den in den Normalbereichen erzwungenen Werten. Der endgültige Wert von `tm_mday` wird erst festgelegt, wenn `tm_mon` und `tm_year` bestimmt sind. Wenn Sie eine `tm`-Strukturzeit angeben, legen Sie das Feld `tm_isdst` auf Folgendes fest:  
  
-   Null (0) weist darauf hin, dass die Normalzeit gilt.  
  
-   Ein Wert größer als 0 weist darauf hin, dass die Sommerzeit gilt.  
  
-   Ein Wert kleiner als null gibt an, dass der C-Laufzeitbibliothekscode berechnet, ob Normalzeit oder Sommerzeit gilt.  
  
 Die C-Laufzeitbibliothek bestimmt das Sommerzeitverhalten anhand der [ZZ](../../c-runtime-library/reference/tzset.md)-Umgebungsvariable. Wenn `TZ` nicht festgelegt wurde, wird der Aufruf der Win32-API-Funktion [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx) verwendet, um die Informationen zur Sommerzeit vom Betriebssystem abzurufen. Wenn dies fehlschlägt, geht die Bibliothek davon aus, dass die Regeln der Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit angewendet werden. `tm_isdst` ist ein Pflichtfeld. Wenn es nicht festgelegt wird, wird sein Wert nicht definiert und der Rückgabewert dieser Funktionen ist unvorhersehbar. Wenn *timeptr* auf eine `tm`-Struktur verweist, die von einem vorherigen Aufruf von `asctime`, `gmtime` oder `localtime` (oder Varianten dieser Funktionen) zurückgegeben wurde, enthält das Feld `tm_isdst` den richtigen Wert.  
  
 `gmtime` und `localtime` (sowie `_gmtime32`, `_gmtime64`, `_localtime32` und `_localtime64`) verwenden einen einzelnen Puffer pro Thread für die Konvertierung. Wenn Sie diesen Puffer für `mktime`, `_mktime32` oder `_mktime64` bereitstellen, wird der vorherige Inhalt zerstört.  
  
 Diese Funktionen überprüfen ihre Parameter. Handelt es sich bei *timeptr* um einen NULL-Zeiger, wird der ungültige Parameterhandler wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, geben die Funktionen – 1 zurück und legen `errno` auf `EINVAL` fest.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`mktime`|\<time.h>|  
|`_mktime32`|\<time.h>|  
|`_mktime64`|\<time.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_mktime.c  
/* The example takes a number of days  
 * as input and returns the time, the current  
 * date, and the specified number of days.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm  when;  
   __time64_t now, result;  
   int        days;  
   char       buff[80];  
  
   time( &now );  
   _localtime64_s( &when, &now );  
   asctime_s( buff, sizeof(buff), &when );  
   printf( "Current time is %s\n", buff );  
   days = 20;  
   when.tm_mday = when.tm_mday + days;  
   if( (result = mktime( &when )) != (time_t)-1 ) {  
      asctime_s( buff, sizeof(buff), &when );  
      printf( "In %d days the time will be %s\n", days, buff );  
   } else  
      perror( "mktime failed" );  
}  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
Current time is Fri Apr 25 13:34:07 2003  
  
In 20 days the time will be Thu May 15 13:34:07 2003  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Time Management (Uhrzeitverwaltung)](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)