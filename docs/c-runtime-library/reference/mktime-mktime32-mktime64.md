---
title: "mktime, _mktime32, _mktime64"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mktime32"
  - "mktime"
  - "_mktime64"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mktime"
  - "_mktime64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mktime32-Funktion"
  - "_mktime64_Funktion"
  - "Konvertieren von Zeiten"
  - "mktime-Funktion"
  - "mktime32-Funktion"
  - "mktime64-Funktion"
  - "time-Funktionen"
  - "Uhrzeit, Konvertieren"
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
caps.latest.revision: 25
caps.handback.revision: "25"
ms.author: "corob"
manager: "ghogen"
---
# mktime, _mktime32, _mktime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert die Ortszeit in einen Kalenderwert.  
  
## Syntax  
  
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
  
#### Parameter  
 *timeptr*  
 Zeiger zur Zeitstruktur. Weitere Informationen finden Sie unter [asctime](../../c-runtime-library/reference/asctime-wasctime.md).  
  
## Rückgabewert  
 `_mktime32` gibt die angegebene Kalenderzeit zurück, die als Wert des [time\_t](../../c-runtime-library/standard-types.md)\-Typs codiert ist. Wenn *timeptr* auf ein Datum vor Mitternacht, 1. Januar 1970 verweist oder die Kalenderzeit nicht dargestellt werden kann, gibt `_mktime32` den Wert –1 zurück, der in den `time_t`\-Typ umgewandelt wird. Verwendung von `_mktime32` und *Timeptr* auf ein Datum nach 23:59:59 am 18. Januar 2038 Coordinated Universal Time \(UTC\), wird zurückgegeben, die in den Typ umgewandelt \-1 `time_t`.  
  
 `_mktime64` gibt den in den `__time64_t`\-Typ umgewandelten Wert –1 zurück, wenn *timeptr* auf ein Datum nach 23:59:59, 31. Dezember 3000 \(UTC\) verweist.  
  
## Hinweise  
 Die Funktionen `mktime`, `_mktime32` und `_mktime64` konvertieren die angegebene Zeitstruktur \(möglicherweise unvollständig\), auf die durch *timeptr* verwiesen wird, in eine vollständig definierte Struktur mit normalisierten Werten. Anschließend konvertieren sie die Struktur in einen `time_t`\-Kalenderzeitwert. Die konvertierte Zeit hat dieselbe Codierung wie die Werte, die von der [time](../../c-runtime-library/reference/time-time32-time64.md)\-Funktion zurückgegeben wurden. Die ursprünglichen Werte der Komponenten `tm_wday` und `tm_yday` der *timeptr*\-Struktur werden ignoriert, und die ursprünglichen Werte der anderen Komponenten werden nicht auf die Normbereiche beschränkt.  
  
 `mktime` ist eine Inlinefunktion, die `_mktime64` entspricht, es sei denn, dass `_USE_32BIT_TIME_T` definiert ist. In diesem Fall entspricht sie `_mktime32`.  
  
 Nach einer Anpassung UTC `_mktime32` behandelt Datumsangaben von Mitternacht, 1. Januar 1970 bis 23:59:59 am 18. Januar 2038 UTC.`_mktime64` behandelt Datumsangaben von Mitternacht, 1. Januar 1970 bis 23:59:59, 31. Dezember 3000. 	Aufgrund dieser Anpassung geben diese Funktionen möglicherweise \-1 zurück \(umgewandelt in `time_t`, `__time32_t` oder `__time64_t`\), obwohl das von Ihnen angegebene Datum innerhalb des Bereichs liegt. Wenn Sie sich zum Beispiel in Kairo \(Ägypten\) aufhalten, das zwei Stunden vor UTC liegt, werden die zwei Stunden zunächst vom Datum subtrahiert, das Sie in *timeptr* angeben. Hierdurch liegt das Datum nun möglicherweise außerhalb des zulässigen Bereichs.  
  
 Diese Funktionen können zum Überprüfen und Ausfüllen einer tm\-Struktur verwendet werden. Bei Erfolg legen diese Funktionen ggf. die Werte aus `tm_wday` und `tm_yday` fest. Die anderen Komponenten werden so festgelegt, dass die angegebene Kalenderzeit dargestellt wird, jedoch mit den in den Normalbereichen erzwungenen Werten. Der endgültige Wert von `tm_mday` wird erst festgelegt, wenn `tm_mon` und `tm_year` bestimmt sind. Wenn Sie eine `tm`\-Strukturzeit angeben, legen Sie das Feld `tm_isdst` auf Folgendes fest:  
  
-   Null \(0\) weist darauf hin, dass die Normalzeit gilt.  
  
-   Ein Wert größer als 0 weist darauf hin, dass die Sommerzeit gilt.  
  
-   Ein Wert kleiner als null gibt an, dass der C\-Laufzeitbibliothekscode berechnet, ob Normalzeit oder Sommerzeit gilt.  
  
 Die C\-Laufzeitbibliothek bestimmt das Sommerzeitverhalten anhand der [TZ](../../c-runtime-library/reference/tzset.md)\-Umgebungsvariablen. Wenn `TZ` nicht festgelegt ist, den Win32\-API\-Aufruf [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx) wird verwendet, um die Sommerzeit vom Betriebssystem Informationen abzurufen. Wenn dies fehlschlägt, geht die Bibliothek davon aus, dass die Regeln der Vereinigten Staaten für die Implementierung der Berechnung der Sommerzeit angewendet werden.`tm_isdst` ist ein Pflichtfeld. Wenn es nicht festgelegt wird, wird sein Wert nicht definiert und der Rückgabewert dieser Funktionen ist unvorhersehbar. Wenn *timeptr* auf eine `tm`\-Struktur verweist, die von einem vorherigen Aufruf von `asctime`, `gmtime` oder `localtime` zurückgegeben wurde \(oder Varianten dieser Funktionen\), enthält das Feld `tm_isdst` den richtigen Wert.  
  
 `gmtime` und `localtime` \(sowie `_gmtime32`, `_gmtime64`, `_localtime32` und `_localtime64`\) verwenden einen einzelnen Puffer pro Thread für die Konvertierung. Wenn Sie diesen Puffer für `mktime`, `_mktime32` oder `_mktime64` bereitstellen, wird der vorherige Inhalt zerstört.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn *Timeptr* null\-Zeiger, der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, geben die Funktionen – 1 zurück und legen `errno` auf `EINVAL` fest.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`mktime`|\<time.h\>|  
|`_mktime32`|\<time.h\>|  
|`_mktime64`|\<time.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
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
  
## Beispielausgabe  
  
```  
Current time is Fri Apr 25 13:34:07 2003  
  
In 20 days the time will be Thu May 15 13:34:07 2003  
```  
  
## .NET Framework-Entsprechung  
 <xref:System.DateTimeOffset.#ctor*>  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)