---
title: "asctime, _wasctime"
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
  - "_wasctime"
  - "asctime"
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
  - "_tasctime"
  - "asctime"
  - "_wasctime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tasctime-Funktion"
  - "_wasctime-Funktion"
  - "asctime-Funktion"
  - "tasctime-Funktion"
  - "Zeitstrukturkonvertierung"
  - "Uhrzeit, Konvertieren"
  - "wasctime-Funktion"
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# asctime, _wasctime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeitstruktur `tm` in eine Zeichenfolge.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
## Syntax  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### Parameter  
 `timeptr`  
 Datum\-\/Uhrzeit\-Struktur.  
  
## Rückgabewert  
 `asctime` gibt einen Zeiger auf Zeichenfolgenergebnis zurück; `_wasctime` gibt einen Zeiger z Zeichenfolge mit Breitzeichenen\-Ergebnis zurück.  Es gibt keinen Fehlerrückgabewert.  
  
## Hinweise  
 Sicherere Versionen dieser Funktionen sind verfügbar; finden Sie unter [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
 Die `asctime`\-Funktion konvertiert eine Zeit, die als Struktur einer Zeichenfolge gespeichert ist.  Der Wert `timeptr` wird normalerweise von einem Aufruf von `gmtime` oder `localtime`, die beide einen Zeiger auf eine Struktur `tm` zurückgeben, die in TIME.H. erhalten.  
  
|timeptr Member|Wert|  
|--------------------|----------|  
|`tm_hour`|Stunden ab Mitternacht \(0\-23\)|  
|`tm_isdst`|Positiv, wenn Sommerzeit wirksam ist; 0 die Sommerzeit nicht aktiv ist; Negativ, wenn Status der Sommerzeit nicht bekannt ist.  Die C\-Laufzeitbibliothek die akzeptiert der Vereinigten Staaten Regeln zum Implementieren der Berechnung der Sommerzeit \(DST\) an.|  
|`tm_mday`|Tag des Monats \(1\-31\)|  
|`tm_min`|Minuten nach Stunde \(0\-59\)|  
|`tm_mon`|Monat \(0\-11; Januar \= 0\)|  
|`tm_sec`|Sekunden nach Minute \(0\-59\)|  
|`tm_wday`|Wochentag \(0\-6; Sonntag \= 0\)|  
|`tm_yday`|Tag des Jahres \(0\-365; Am 1. Januar \= 0\)|  
|`tm_year`|Jahr \(Open\-Wheel\-Racing\-Team Jahr minus 1900\)|  
  
 Die konvertierte Zeichenfolge wird auch nach den Einstellungen der lokalen Zeitzone angepasst.  Informationen zum Konfigurieren der Ortszeit, finden Sie unter [time](../../c-runtime-library/reference/time-time32-time64.md), [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)\-Funktionen und die [\_tzset](../../c-runtime-library/reference/tzset.md)\-Funktion zu Informationen über das Definieren der Zeitzonenumgebung und der globalen Variablen.  
  
 Das Zeichenfolgenergebnis, das von `asctime` erzeugt wird, enthält genau 26 Zeichen und weist das Format `Wed Jan 02 02:03:55 1980\n\0`.  Ein 24\-Stunden\-Format wird verwendet.  Alle Felder verfügen eine konstante Breite.  Das Zeilenumbruchzeichen und das Nullzeichen nehmen die letzten zwei Positionen der Zeichenfolge ein.  `asctime` verwendet einen einzelnen, statisch zugehörigen Puffer, um die Rückgabezeichenfolge aufzunehmen.  Jeder Aufruf dieser Funktion zerstört das Ergebnis der vorherigen Aufrufs.  
  
 `_wasctime` ist eine Breitzeichenversion von `asctime`.  `_wasctime` und `asctime` verhalten sich andernfalls identisch.  
  
 Diese Funktionen überprüfen ihre Parameter.  Wenn `timeptr` ein NULL\-Zeiger ist oder wenn er außerhalb des Gültigkeitsbereichs liegenden Werte enthält, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion `NULL` zurück und setzt `errno` auf `EINVAL`.  
  
### Zuordnung generische Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`asctime`|\<time.h\>|  
|`_wasctime`|\<time.h oder\> wchar.h \<\>|  
  
## Beispiel  
 Dieses Programm platziert die Systemzeit in langen ganzzahligen `aclock`, übersetzt sie in die `newtime`\-Struktur und konvertiert sie anschließend in Zeichenfolgenform für Ausgaben, mit der `asctime`\-Funktion.  
  
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
  
  **Aktuelles Datum und Uhrzeit: Sun am 3. Februar 11: 38:58 2002**   
## .NET Framework-Entsprechung  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)