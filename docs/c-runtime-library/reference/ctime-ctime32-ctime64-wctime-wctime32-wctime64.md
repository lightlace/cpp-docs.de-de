---
title: "ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ctime64"
  - "_wctime32"
  - "ctime"
  - "_wctime64"
  - "_ctime32"
  - "_wctime"
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
  - "_wctime64"
  - "_ctime32"
  - "_tctime"
  - "_wctime"
  - "_wctime32"
  - "_tctime64"
  - "_ctime64"
  - "ctime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tctime64-Funktion"
  - "_ctime32-Funktion"
  - "ctime32-Funktion"
  - "_wctime-Funktion"
  - "wctime64-Funktion"
  - "_tctime64-Funktion"
  - "_tctime32-Funktion"
  - "_ctime64-Funktion"
  - "_wctime64-Funktion"
  - "ctime-Funktion"
  - "wctime32-Funktion"
  - "ctime64-Funktion"
  - "_wctime32-Funktion"
  - "_tctime-Funktion"
  - "tctime32-Funktion"
  - "tctime-Funktion"
  - "wctime-Funktion"
  - "Uhrzeit, Konvertieren"
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertieren Sie einen Zeitwert in eine Zeichenfolge, und passen Sie für die lokale Zeit Einstellungen. Sicherere Versionen dieser Funktionen sind verfügbar. finden Sie unter [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).  
  
## Syntax  
  
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
  
#### Parameter  
 `timer`  
 Ein Zeiger auf die gespeicherte Zeit.  
  
## Rückgabewert  
 Ein Zeiger auf das Ergebnis die Zeichen der Zeichenfolge.`NULL` Wenn zurückgegeben:  
  
-   `time` ein Datum vor Mitternacht, 1. Januar 1970 UTC darstellt.  
  
-   Bei Verwendung von `_ctime32` oder `_wctime32` und `time` ein Datum nach 23:59:59 am 18. Januar 2038 UTC darstellt.  
  
-   Bei Verwendung von `_ctime64` oder `_wctime64` und `time` ein Datum nach 23:59:59, 31. Dezember 3000 UTC darstellt.  
  
 `ctime` ist eine Inlinefunktion bewertet, um `_ctime64` und `time_t` entspricht `__time64_t`. Möchten Sie den Compiler, interpretieren erzwingen `time_t` als das alte 32\-Bit `time_t`, können `_USE_32BIT_TIME_T`. Dadurch wird `ctime` ergibt `_ctime32`. Dies wird nicht empfohlen, da die Anwendung nach dem 18. Januar 2038 fehlschlägt und sie wird auf 64\-Bit\-Plattformen nicht zugelassen.  
  
## Hinweise  
 Die `ctime` \-Funktion konvertiert einen Zeitwert als ein [Time\_t](../../c-runtime-library/standard-types.md) Wert in eine Zeichenfolge. Die `timer` Wert wird normalerweise von einem Aufruf abgerufen [Zeit](../../c-runtime-library/reference/time-time32-time64.md), welche gibt die Anzahl der Sekunden seit Mitternacht vergangenen \(00: 00:00\), 1. Januar 1970, koordinierte Weltzeit \(UTC\). Die Rückgabewert Zeichenfolge genau 26 Zeichen enthält und weist folgende Form:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24\-Stunden\-Format wird verwendet. Alle Felder weisen eine Konstante Breite. Das Zeilenumbruchzeichen \('\\n'\) und das Null\-Zeichen \('\\0'\) belegen die letzten beiden Stellen der Zeichenfolge.  
  
 Die konvertierte Zeichenfolge wird auch die Ortszeit Einstellungen angepasst. Finden Sie unter der `time`, [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), und [Localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) Funktionen Informationen zum Konfigurieren der lokalen Zeit und die [\_tzset](../../c-runtime-library/reference/tzset.md) Funktion ausführliche Informationen zum Definieren der Zeitzone Umgebung und globale Variablen.  
  
 Ein Aufruf von `ctime` ändert der einzelnen statisch zugewiesenen Puffer für die `gmtime` und `localtime` Funktionen. Jeder Aufruf dieser Routinen zerstört das Ergebnis des vorherigen Aufrufs.`ctime` Teilt einen statischen Puffer mit der `asctime` Funktion. Folglich einen Aufruf von `ctime` Löscht die Ergebnisse von einem vorherigen Aufruf von `asctime`, `localtime`, oder `gmtime`.  
  
 `_wctime` und `_wctime64` sind die Breitzeichen\-Version der `ctime` und `_ctime64`; die Rückgabe eines Zeigers auf Breitzeichen\-Zeichenfolge. Andernfalls `_ctime64`, `_wctime`, und `_wctime64` Verhalten sich genauso wie `ctime`.  
  
 Diese Funktionen überprüfen ihre Parameter. Wenn `timer` ein null\-Zeiger ist oder wenn der Zeitwert negativ ist, rufen diese Funktionen den Handler für ungültige Parameter an, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und setzt `errno` auf `EINVAL`.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`ctime`|\<time.h\>|  
|`_ctime32`|\<time.h\>|  
|`_ctime64`|\<time.h\>|  
|`_wctime`|\< time.h \> oder \< wchar.h \>|  
|`_wctime32`|\< time.h \> oder \< wchar.h \>|  
|`_wctime64`|\< time.h \> oder \< wchar.h \>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
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
Die Zeit ist Mi, 13 Feb 16:04:43 2002  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)