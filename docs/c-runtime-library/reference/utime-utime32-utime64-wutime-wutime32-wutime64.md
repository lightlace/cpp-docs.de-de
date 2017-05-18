---
title: _utime, _utime32, _utime64, _wutime, _wutime32, _wutime64 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _utime64
- _utime
- _wutime
- _wutime64
- _wutime32
- _utime32
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
- _tutime
- _utime64
- wutime
- utime32
- wutime64
- _utime
- wutime32
- _wutime
- utime
- utime64
- _wutime64
- _utime32
- _tutime64
- _wutime32
dev_langs:
- C++
helpviewer_keywords:
- tutime function
- utime32 function
- utime64 function
- _utime function
- _tutime32 function
- time [C++], file modification
- wutime function
- _wutime function
- _wutime32 function
- _tutime64 function
- _tutime function
- files [C++], modification time
- _wutime64 function
- _utime32 function
- utime function
- _utime64 function
- wutime64 function
- wutime32 function
- tutime64 function
- tutime32 function
ms.assetid: 8d482d40-19b9-4591-bfee-5d7f601d1a9e
caps.latest.revision: 16
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
ms.openlocfilehash: 80836179c63da2f62384abd07fe2a4970d9bce55
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="utime-utime32-utime64-wutime-wutime32-wutime64"></a>_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64
Legen Sie die Dateiänderungszeit fest.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Zeiger auf eine Zeichenfolge, die den Pfad oder Dateiname enthält.  
  
 `times`  
 Zeiger auf die gespeicherten Zeitwerte.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt „0“ zurück, wenn die Dateiänderungszeit geändert wurde. Ein Rückgabewert von – 1 zeigt einen Fehler. Wird ein ungültiger Parameter übergeben, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen -1 zurück und setzen `errno` auf einen der folgenden Werte:  
  
 `EACCES`  
 Pfad gibt Verzeichnis oder schreibgeschützte Datei an.  
  
 `EINVAL`  
 Ungültiges Argument `times`.  
  
 `EMFILE`  
 Zu viele Dateien geöffnet. (Die Datei muss geöffnet werden, damit die Änderungszeit geändert werden kann.)  
  
 `ENOENT`  
 Pfad oder Dateiname wurde nicht gefunden.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Wenn das Datum der Änderung nach dem 1. Januar 1970, Mitternacht, und vor dem Enddatum für die Verwendung der Funktion liegt, kann das Datum für eine Datei geändert werden. `_utime` und `_wutime` verwenden einen 64-Bit-Zeitwert, sodass das Enddatum der 31. Dezember 3000, 23:59:59 UTC ist. Wenn `_USE_32BIT_TIME_T` so definiert wurde, dass das alte Verhalten erzwungen wird, ist das Enddatum der 18. Januar 2038, 23:59:59 UTC. `_utime32` und `_wutime32` verwenden einen 32-Bit-Zeittyp, unabhängig davon, ob `_USE_32BIT_TIME_T` definiert wurde, und weisen immer das frühere Enddatum auf. `_utime64` und `_wutime64` verwenden immer den 64-Bit-Zeittyp, sodass von diesen Funktionen immer das spätere Enddatum unterstützt wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `_utime`-Funktion legt die Änderungszeit für die durch `filename` *angegebene Datei fest.* Damit die Zeit geändert werden kann, benötigt der Prozess Schreibzugriff für die Datei. Im Betriebssystem Windows können Zugriffszeit und Änderungszeit in der `_utimbuf`-Struktur geändert werden. Wenn `times` ein `NULL`-Zeiger ist, wird die Änderungszeit auf die aktuelle Ortszeit festgelegt. Andernfalls muss `times` auf eine Struktur vom Typ `_utimbuf` zeigen, die in SYS\UTIME.H definiert ist.  
  
 Die `_utimbuf`-Struktur speichert die Dateizugriffs- und Änderungszeiten, die von `_utime` verwendet wird, um Datumsangaben zu Dateiänderungen zu ändern. Die Struktur weist die folgenden Felder auf, die beide vom Typ `time_t` sind:  
  
 `actime`  
 Uhrzeit des Dateizugriffs  
  
 `modtime`  
 Uhrzeit der Dateiänderung  
  
 Bestimmte Versionen der Struktur `_utimbuf` (`_utimebuf32` und `__utimbuf64`) werden mit den 32-Bit- und 64-Bit-Versionen des Zeittyps definiert. Diese werden in den 32-Bit- und 64-Bit-spezifischen Versionen dieser Funktion verwendet. `_utimbuf` selbst verwendet standardmäßig einen 64-Bit-Zeittyp, sofern nicht `_USE_32BIT_TIME_T` definiert wird.  
  
 `_utime` ist mit `_futime` bis auf die Tatsache identisch, dass das `filename`-Argument von `_utime` ein Dateiname oder ein Pfad zu einer Datei ist und keinen Dateideskriptor einer geöffneten Datei darstellt.  
  
 `_wutime` ist eine Breitzeichenversion von `_utime`. Das `filename`-Argument für `_wutime` ist eine Breitzeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tutime`|`_utime`|`_utime`|`_wutime`|  
|`_tutime32`|`_utime32`|`_utime32`|`_wutime32`|  
|`_tutime64`|`_utime64`|`_utime64`|`_wutime64`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderliche Header|Optionale Header|  
|-------------|----------------------|----------------------|  
|`_utime`, `_utime32`, `_utime64`|\<sys/utime.h>|\<errno.h>|  
|`_utime64`|\<sys/utime.h>|\<errno.h>|  
|`_wutime`|\<utime.h> oder \<wchar.h>|\<errno.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Dieses Programm verwendet `_utime`, um die Dateiänderungszeit auf die aktuelle Zeit festzulegen.  
  
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
  
## <a name="sample-output"></a>Beispielausgabe  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [_futime, _futime32, _futime64](../../c-runtime-library/reference/futime-futime32-futime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_stat-, _wstat-Funktionen](../../c-runtime-library/reference/stat-functions.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
