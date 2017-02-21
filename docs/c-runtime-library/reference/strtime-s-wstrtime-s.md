---
title: "_strtime_s, _wstrtime_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wstrtime_s"
  - "_strtime_s"
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
  - "_wstrtime_s"
  - "strtime_s"
  - "wstrtime_s"
  - "_strtime_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtime_s-Funktion"
  - "_wstrtime_s-Funktion"
  - "Kopieren der Uhrzeit in Puffer"
  - "strtime_s-Funktion"
  - "Uhrzeit, Kopieren"
  - "wstrtime_s-Funktion"
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _strtime_s, _wstrtime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kopieren Sie die aktuelle Uhrzeit in einem Puffer.  Diese Versionen sind von [\_strtime, \_wstrtime](../../c-runtime-library/reference/strtime-wstrtime.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _strtime_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrtime_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strtime_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrtime_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `buffer`  
 Ein Puffer, mindestens 10 Bytes lang, wo die Zeit geschrieben wird.  
  
 \[in\] `numberOfElements`  
 Die Größe des Puffers.  
  
## Rückgabewert  
 Null wenn erfolgreich.  
  
 Wenn ein Fehlerzustand auftritt, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt.  Fehlercodes werden in ERRNO.H definiert; finden Sie in der folgenden Tabelle für die genaue Fehler, die von dieser Funktion generiert werden.  Weitere Informationen zu Fehlercodes, finden Sie unter [errno Konstanten](../../c-runtime-library/errno-constants.md).  
  
### Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|Return|Inhalt von `buffer`|  
|--------------|------------------------|------------|-------------------------|  
|`NULL`|\(alle\)|`EINVAL`|Nicht geändert|  
|Nicht `NULL` \(Zeiger auf gültigen Puffer\)|0|`EINVAL`|Nicht geändert|  
|Nicht `NULL` \(Zeiger auf gültigen Puffer\)|0 \< Größe \< 9|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL` \(Zeiger auf gültigen Puffer\)|Größe \> 9|0|Aktuelle Uhrzeit formatiert, wie in den Hinweisen angegeben|  
  
## Sicherheitsprobleme  
 Die Übergabe in einen ungültigen Wert ungleich null für den Puffer ergibt eine Zugriffsverletzung, wenn der `numberOfElements`\-Parameter größer als 9. ist.  
  
 Das Übergeben eines Werts für `numberOfElements`, der größer ist, als das tatsächliche Größe des Puffers wird Pufferüberlauf.  
  
## Hinweise  
 Diese Funktionen stellen sicherere Versionen von `_strtime` und `_wstrtime`.  Die `_strtime_s`\-Funktion wird die aktuelle Ortszeit in den Puffer, auf den durch `timestr` gezeigt wird *.* Die Zeit wird als `hh:mm:ss`, wobei `hh` zwei Ziffern ist, die die Uhrzeit im 24 der Notation `mm` darstellen, werden zwei Ziffern formatiert, die die Minuten nach der Stunde darstellen, und `ss` sind zwei Ziffern, die darstellen Sekunden.  Beispielsweise stellt die Zeichenfolge `18:23:44` 23 Minuten und 44 Sekunden nach 6 Uhr dar Der Puffer muss mindestens 9 Bytes lang sein; Originalgröße wird das durch den zweiten Parameter angegeben.  
  
 `_wstrtime` ist eine Breitzeichenversion von `_strtime`. Das Argument und der Rückgabewert von `_wstrtime` sind Zeichenfolgen mit Breitzeichen.  Anderenfalls verhalten sich diese Funktionen identisch.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen:  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tstrtime_s`|`_strtime_s`|`_strtime_s`|`_wstrtime_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_strtime_s`|\<time.h\>|  
|`_wstrtime_s`|\<time.h oder\> wchar.h \<\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// strtime_s.c  
  
#include <time.h>  
#include <stdio.h>  
  
int main()  
{  
    char tmpbuf[9];  
    errno_t err;  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    // Display operating system-style date and time.   
    err = _strtime_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
      exit(1);  
    }  
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );  
    err = _strdate_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
       exit(1);  
    }  
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );  
  
}  
```  
  
  **Betriebssystem\-Zeit:            14:37: 49**  
**Betriebssystemdatum:            04\/25\/03**   
## .NET Framework-Entsprechung  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)