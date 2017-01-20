---
title: "_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_utime64"
  - "_utime"
  - "_wutime"
  - "_wutime64"
  - "_wutime32"
  - "_utime32"
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
  - "_tutime"
  - "_utime64"
  - "wutime"
  - "utime32"
  - "wutime64"
  - "_utime"
  - "wutime32"
  - "_wutime"
  - "utime"
  - "utime64"
  - "_wutime64"
  - "_utime32"
  - "_tutime64"
  - "_wutime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tutime-Funktion"
  - "utime32-Funktion"
  - "utime64-Funktion"
  - "_utime-Funktion"
  - "_tutime32-Funktion"
  - "Uhrzeit [C++], Dateiänderung"
  - "wutime-Funktion"
  - "_wutime-Funktion"
  - "_wutime32-Funktion"
  - "_tutime64-Funktion"
  - "_tutime-Funktion"
  - "Dateien [C++], Änderungszeit"
  - "_wutime64-Funktion"
  - "_utime32-Funktion"
  - "utime-Funktion"
  - "_utime64-Funktion"
  - "wutime64-Funktion"
  - "wutime32-Funktion"
  - "tutime64-Funktion"
  - "tutime32-Funktion"
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legen Sie die Änderungszeit der Datei.  
  
## Syntax  
  
```  
int _utime(  
   const char *filename,  
   struct _utimbuf *times   
);  
int _utime32(  
   const char *filename,  
   struct __utimbuf32 *times   
);  
int _utime64(  
   const char *filename,  
   struct __utimbuf64 *times   
);  
int _wutime(  
   const wchar_t *filename,  
   struct _utimbuf *times   
);  
int _wutime32(  
   const wchar_t *filename,  
   struct __utimbuf32 *times   
);  
int _wutime64(  
   const wchar_t *filename,  
   struct __utimbuf64 *times   
);  
```  
  
#### Parameter  
 `filename`  
 Ein Zeiger auf eine Zeichenfolge, die den Pfad oder Dateinamen enthält.  
  
 `times`  
 Zeiger auf gespeicherte Time\-Werte.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt 0 zurück, wenn die Datei Änderungszeit geändert wurde. Ein Rückgabewert von –1 zeigt einen Fehler an. Wenn ein ungültiger Parameter übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen – 1 zurück und `errno` auf einen der folgenden Werte festgelegt:  
  
 `EACCES`  
 Pfad angibt, Verzeichnis oder eine schreibgeschützte Datei  
  
 `EINVAL`  
 Ungültige `times` Argument  
  
 `EMFILE`  
 Zu viele Dateien geöffnet \(die Datei muss geöffnet werden, um die Änderung zu ändern\)  
  
 `ENOENT`  
 Pfad oder Dateiname wurde nicht gefunden.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Wenn das Datum nach dem 1. Januar 1970, Mitternacht und vor dem Enddatum der Funktion verwendet wird, kann das Datum für eine Datei geändert werden.`_utime` und `_wutime` einen 64\-Bit\-Zeitwert verwenden, damit das Enddatum 23:59:59, 31. Dezember 3000 UTC ist. Wenn `_USE_32BIT_TIME_T` definiert das alte Verhalten zu erzwingen, das Enddatum 23:59:59 am 18. Januar 2038 UTC ist.`_utime32` oder `_wutime32` verwenden einen 32\-Bit\-Uhrzeit\-Typ, unabhängig davon, ob `_USE_32BIT_TIME_T` definiert ist, und immer das frühere Enddatum.`_utime64` oder `_wutime64` verwenden immer den 64\-Bit\-Zeittyp aus, so dass diese Funktionen immer höhere Enddatum unterstützt.  
  
## Hinweise  
 Die `_utime` Funktion legt die Änderungszeit der angegebenen Datei `filename`*.* Der Prozess muss Schreibzugriff auf die Datei verfügen, um die Uhrzeit zu ändern. Sie können in der Windows\-Betriebssystem ändern, die Zeit für den Zugriff und die Uhrzeit der Änderung in die `_utimbuf` Struktur. Wenn `times` ist eine `NULL` \-Zeiger, der Zeitpunkt der Änderung auf die aktuelle lokale Zeit festgelegt ist. Andernfalls `times` muss einen Verweis auf eine Struktur vom Typ `_utimbuf`, die in SYS\\UTIME definiert. H.  
  
 Die `_utimbuf` \-Struktur speichert die Datei und Häufigkeit der Verwendung von `_utime` zum Ändern der Datei ändern. Die Struktur umfasst die folgenden Felder, die beide vom Typ `time_t`:  
  
 `actime`  
 Zeitpunkt des Dateizugriffs  
  
 `modtime`  
 Uhrzeit der dateiänderung  
  
 Bestimmte Versionen von der `_utimbuf` Struktur \(`_utimebuf32` und `__utimbuf64`\) mit den 32\-Bit\- und 64\-Bit\-Versionen vom Time\-Typ definiert werden. Diese werden in die 32\-Bit\- und 64\-Bit\-Versionen dieser Funktion verwendet.`_utimbuf` Standardmäßig verwendet einen 64\-Bit\-Uhrzeit\-Typ, wenn `_USE_32BIT_TIME_T` definiert ist.  
  
 `_utime` ist identisch mit `_futime` mit dem Unterschied, dass die `filename` Argument `_utime` ist ein Dateiname oder ein Pfad zu einer Datei, anstatt einen Dateideskriptor einer geöffneten Datei.  
  
 `_wutime` ist eine Breitzeichenversion von `_utime`. Das `filename`\-Argument für `_wutime` ist eine Breitzeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## Anforderungen  
  
|Routine|Erforderliche Header|Optionale Header|  
|-------------|--------------------------|----------------------|  
|`_utime`, `_utime32`, `_utime64`|\< sys\/utime.h \>|\<errno.h\>|  
|`_utime64`|\< sys\/utime.h \>|\<errno.h\>|  
|`_wutime`|\< utime.h \> oder \< wchar.h \>|\<errno.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Programm verwendet `_utime` beim Ändern der Datei mit der aktuellen Uhrzeit festlegen.  
  
```  
// crt_utime.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <sys/types.h>  
#include <sys/utime.h>  
#include <time.h>  
  
int main( void )  
{  
   struct tm tma = {0}, tmm = {0};  
   struct _utimbuf ut;  
  
   // Fill out the accessed time structure  
   tma.tm_hour = 12;  
   tma.tm_isdst = 0;  
   tma.tm_mday = 15;  
   tma.tm_min = 0;  
   tma.tm_mon = 0;  
   tma.tm_sec = 0;  
   tma.tm_year = 103;  
  
   // Fill out the modified time structure  
   tmm.tm_hour = 12;  
   tmm.tm_isdst = 0;  
   tmm.tm_mday = 15;  
   tmm.tm_min = 0;  
   tmm.tm_mon = 0;  
   tmm.tm_sec = 0;  
   tmm.tm_year = 102;  
  
   // Convert tm to time_t  
   ut.actime = mktime(&tma);  
   ut.modtime = mktime(&tmm);  
  
   // Show file time before and after  
   system( "dir crt_utime.c" );  
   if( _utime( "crt_utime.c", &ut ) == -1 )  
      perror( "_utime failed\n" );  
   else  
      printf( "File time modified\n" );  
   system( "dir crt_utime.c" );  
}  
```  
  
## Beispielausgabe  
  
```  
Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/09/2003  05:38 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
File time modified  
 Volume in drive C has no label.  
 Volume Serial Number is 9CAC-DE74  
  
 Directory of C:\test  
  
01/15/2002  12:00 PM               935 crt_utime.c  
               1 File(s)            935 bytes  
               0 Dir(s)  20,742,955,008 bytes free  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [\_futime, \_futime32, \_futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [\_stat\- und \_wstat\-Funktionen](../../c-runtime-library/reference/stat-functions.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)