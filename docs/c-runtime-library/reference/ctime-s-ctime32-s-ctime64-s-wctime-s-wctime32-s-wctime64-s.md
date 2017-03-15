---
title: "ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ctime64_s"
  - "_wctime32_s"
  - "ctime_s"
  - "_wctime64_s"
  - "_ctime32_s"
  - "_wctime_s"
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
  - "ctime64_s"
  - "_ctime32_s"
  - "_tctime32_s"
  - "_ctime64_s"
  - "_wctime_s"
  - "_tctime_s"
  - "_tctime64_s"
  - "ctime_s"
  - "ctime32_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctime32_s-Funktion"
  - "ctime64_s-Funktion"
  - "_tctime64_s-Funktion"
  - "_wctime_s-Funktion"
  - "tctime_s-Funktion"
  - "_wctime64_s-Funktion"
  - "ctime_s-Funktion"
  - "ctime32_s-Funktion"
  - "_ctime64_s-Funktion"
  - "tctime64_s-Funktion"
  - "wctime64_s-Funktion"
  - "wctime_s-Funktion"
  - "_tctime_s-Funktion"
  - "tctime32_s-Funktion"
  - "wctime32_s-Funktion"
  - "Uhrzeit, Konvertieren"
  - "_ctime32_s-Funktion"
  - "_tctime32_s-Funktion"
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertieren Sie einen Zeitwert in eine Zeichenfolge, und passen Sie für die lokale Zeit Einstellungen. Dies sind die Versionen von [Ctime, \_ctime64, \_wctime, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntax  
  
```  
errno_t ctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _ctime32_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _ctime64_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time64_t *time )  
;  
errno_t _wctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _wctime32_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _wctime64_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time64_t *time   
);  
template <size_t size>  
errno_t _ctime32_s(   
   char (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _ctime64_s(   
   char (&buffer)[size],  
   const __time64_t *time  
); // C++ only  
template <size_t size>  
errno_t _wctime32_s(   
   wchar_t (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _wctime64_s(   
   wchar_t (&buffer)[size],  
   const __time64_t *time   
); // C++ only  
```  
  
#### Parameter  
 \[out\] `buffer`  
 Muss groß genug für 26 Zeichen sein. Ein Zeiger auf das Ergebnis der Zeichenfolge Zeichen oder `NULL`wenn:  
  
-   `time` ein Datum vor Mitternacht, 1. Januar 1970 UTC darstellt.  
  
-   Bei Verwendung von `_ctime32_s` oder `_wctime32_s` und `time` ein Datum nach 23:59:59 am 18. Januar 2038 UTC darstellt.  
  
-   Bei Verwendung von `_ctime64_s` oder `_wctime64_s` und `time` ein Datum nach 23:59:59, 31. Dezember 3000 UTC darstellt.  
  
-   Bei Verwendung von `_ctime_s` oder `_wctime_s`, diese Funktionen sind Wrapper für die zuvor genannten Funktionen. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 \[in\] `numberOfElements`  
 Die Größe des Puffers.  
  
 \[in\] t`ime`  
 Ein Zeiger auf die gespeicherte Zeit.  
  
## Rückgabewert  
 NULL, wenn erfolgreich. Ist ein Fehler aufgrund eines ungültigen Parameters, wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, wird ein Fehlercode zurückgegeben. Fehlercodes sind in ERRNO definiert. H; eine Liste dieser Fehler finden Sie unter [Errno](../../c-runtime-library/errno-constants.md). Die tatsächliche Fehlercodes für jeden Fehler ausgelöst werden in der folgenden Tabelle angezeigt.  
  
## Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|`time`|Zurück|Wert in `buffer`|  
|--------------|------------------------|------------|------------|----------------------|  
|`NULL`|any|any|`EINVAL`|Nicht geändert|  
|Nicht `NULL` \(verweist auf gültige Speicher\)|0|any|`EINVAL`|Nicht geändert|  
|Nicht `NULL`|0 \< \< 26 Größe|any|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL`|\>\= 26|NULL|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL`|\>\= 26|\< 0|`EINVAL`|Leere Zeichenfolge|  
  
## Hinweise  
 Die `ctime_s` \-Funktion konvertiert einen Zeitwert als ein [Time\_t](../../c-runtime-library/standard-types.md) Struktur in eine Zeichenfolge. Die `time` Wert wird normalerweise von einem Aufruf abgerufen [Zeit](../../c-runtime-library/reference/time-time32-time64.md), welche gibt die Anzahl der Sekunden seit Mitternacht vergangenen \(00: 00:00\), 1. Januar 1970, koordinierte Weltzeit \(UTC\). Die Rückgabewert Zeichenfolge genau 26 Zeichen enthält und weist folgende Form:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24\-Stunden\-Format wird verwendet. Alle Felder weisen eine Konstante Breite. Das Zeilenumbruchzeichen \('\\n'\) und das Null\-Zeichen \('\\0'\) belegen die letzten beiden Stellen der Zeichenfolge.  
  
 Die konvertierte Zeichenfolge wird auch die Ortszeit Einstellungen angepasst. Finden Sie unter der `time`, [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), und [localtime32\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) Funktionen Informationen zum Konfigurieren der lokalen Zeit und die [\_tzset](../../c-runtime-library/reference/tzset.md) Funktion Informationen zu Zeitzonen\-Umgebung und globale Variablen definiert.  
  
 `_wctime32_s` und `_wctime64_s` sind die Breitzeichen\-Version der `_ctime32_s` und `_ctime64_s`; die Rückgabe eines Zeigers auf Breitzeichen\-Zeichenfolge. Andernfalls `_ctime64_s`, `_wctime32_s`, und `_wctime64_s` Verhalten sich genauso wie `_ctime32_s`.  
  
 `ctime_s` ist eine Inlinefunktion, der ergibt `_ctime64_s` und `time_t` entspricht `__time64_t`. Wenn Sie den Compiler zwingen müssen, `time_t` als das alte 32\-Bit\-`time_t` zu interpretieren, definieren Sie `_USE_32BIT_TIME_T`. Dadurch wird `ctime_s` ergibt `_ctime32_s`. Dies wird nicht empfohlen, da die Anwendung nach dem 18. Januar 2038 fehlschlägt und sie wird auf 64\-Bit\-Plattformen nicht zugelassen.  
  
 Die Verwendung dieser Funktionen in C\+\+ wird durch Überladungen \(als Vorlagen vorhanden\) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`ctime_s,`<br /><br /> `_ctime32_s,`<br /><br /> `_ctime64_s`|\<time.h\>|  
|`_wctime_s,`<br /><br /> `_wctime32_s,`<br /><br /> `_wctime64_s`|\< time.h \> oder \< wchar.h \>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_wctime_s.c  
/* This program gets the current  
 * time in time_t form and then uses _wctime_s to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
#define SIZE 26  
  
int main( void )  
{  
   time_t ltime;  
   wchar_t buf[SIZE];  
   errno_t err;  
  
   time( &ltime );  
  
   err = _wctime_s( buf, SIZE, &ltime );  
   if (err != 0)  
   {  
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);  
   }  
   wprintf_s( L"The time is %s\n", buf );  
}  
```  
  
## Beispielausgabe  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)