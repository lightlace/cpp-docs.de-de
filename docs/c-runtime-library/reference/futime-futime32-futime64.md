---
title: "_futime, _futime32, _futime64"
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
  - "_futime64"
  - "_futime32"
  - "_futime"
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
  - "futime"
  - "_futime"
  - "futime64"
  - "_futime64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_futime-Funktion"
  - "futime32-Funktion"
  - "futime64-Funktion"
  - "Dateiänderungszeit [C++]"
  - "_futime64-Funktion"
  - "futime-Funktion"
  - "_futime32-Funktion"
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
caps.latest.revision: 21
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# _futime, _futime32, _futime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Änderungszeit auf einer geöffneten Datei fest.  
  
## Syntax  
  
```  
int _futime(   
   int fd,  
   struct _utimbuf *filetime   
);  
int _futime32(   
   int fd,  
   struct __utimbuf32 *filetime   
);  
int _futime64(   
   int fd,  
   struct __utimbuf64 *filetime   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor der geöffneten Datei.  
  
 `filetime`  
 Zeiger zur Struktur, die das neue Änderungsdatum enthält.  
  
## Rückgabewert  
 EINGABETASTE, wenn 0 erfolgreich.  Wenn ein Fehler auftritt, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, kehrt die Funktion zurück \- 1 und `errno` ist auf `EBADF` festgelegt und gibt ein ungültiges Dateideskriptor oder `EINVAL` an und gibt ein ungültiges Parameter an.  
  
## Hinweise  
 Die Routine `_futime` legt das Änderungsdatum und die Zugriffsgeschwindigkeit auf der geöffneten Datei fest, die `fd` zugeordnet ist *.* `_futime` wird [\_utime](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) identisch, nur dass Argument ist der Dateideskriptor einer geöffneten Datei, und der Name einer Datei oder eines Pfads zu einer Datei.  Die `_utimbuf`\-Struktur enthält Felder während des neuen Änderungsdatums und \-Zugriffsgeschwindigkeit.  Beide Felder müssen gültige Werte enthalten.  `_utimbuf32` und `_utimbuf64` sind in `_utimbuf` außer dem Verwendung des 32\-Bit identisch und 64\-Bit\-Zeit gibt, bzw. ein.  `_futime` und `_utimbuf` verwenden einen 64\-Bit\-Zeittyp und `_futime` ist im Verhalten mit `_futime64` identisch.  Wenn Sie das alte Verhalten erzwingen muss, definieren Sie `_USE_32BIT_TIME_T`.  Hierdurch wird `_futime32``_futime`, im Verhalten identisch sein und bewirkt die Struktur `_utimbuf`, den 32\-Bit\-Zeittyp verwendet und macht sie äquivalent zu `__utimbuf32`.  
  
 `_futime64`, die die Struktur `__utimbuf64` verwendet, kann Dateidatumsangaben 23:59 lesen und ändern: 59 3000 am 31. Dezember, UTC; während ein Aufruf von `_futime32` fehlschlägt, ob das Datum auf der Datei später von 19:14 ist: Am 7. Januar 18 2038, UTC.  Mitternacht am 1. Januar 1970 ist die untere Begrenzung des Zeitraums für diese Funktionen.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|Optionaler Header|  
|--------------|---------------------------|-----------------------|  
|`_futime`|\<sys\/utime.h\>|\<errno.h\>|  
|`_futime32`|\<sys\/utime.h\>|\<errno.h\>|  
|`_futime64`|\<sys\/utime.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_futime.c  
// This program uses _futime to set the  
// file-modification time to the current time.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <io.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/utime.h>  
#include <share.h>  
  
int main( void )  
{  
   int hFile;  
  
   // Show file time before and after.   
   system( "dir crt_futime.c_input" );  
  
   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );  
  
   if( _futime( hFile, NULL ) == -1 )  
      perror( "_futime failed\n" );  
   else  
      printf( "File time modified\n" );  
  
   _close (hFile);  
  
   system( "dir crt_futime.c_input" );  
}  
```  
  
## Eingabe: crt\_futime.c\_input  
  
```  
Arbitrary file contents.  
```  
  
### Beispielausgabe  
  
```  
Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:40 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
 Volume in drive Z has no label.  
 Volume Serial Number is 5C68-57C1  
  
 Directory of Z:\crt  
  
03/25/2004  10:41 AM                24 crt_futime.c_input  
               1 File(s)             24 bytes  
               0 Dir(s)  24,268,476,416 bytes free  
File time modified  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::File::SetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastaccesstime.aspx)  
  
-   [System::IO::File::SetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.setlastwritetime.aspx)  
  
-   [System::IO::File::SetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.setcreationtime.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)