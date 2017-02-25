---
title: "_lseek, _lseeki64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lseeki64"
  - "_lseek"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_lseeki64"
  - "_lseek"
  - "lseeki64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lseek-Funktion"
  - "_lseeki64-Funktion"
  - "Dateizeiger [C++], Verschieben"
  - "lseek-Funktion"
  - "lseeki64-Funktion"
  - "seek-Dateizeiger"
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _lseek, _lseeki64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verschiebt Dateizeiger einen auf der angegebenen Position.  
  
## Syntax  
  
```  
  
      long _lseek(  
   int fd,  
   long offset,  
   int origin   
);  
__int64 _lseeki64(  
   int fd,  
   __int64 offset,  
   int origin   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor, der eine geöffnete Datei verweist.  
  
 *offset*  
 Anzahl Bytes *vom Ursprung*.  
  
 *Ursprung*  
 Startposition.  
  
## Rückgabewert  
 `_lseek` gibt den Offset, in Bytes, der neuen Position am Anfang der Datei.  `_lseeki64` gibt den Offset in einer 64\-Bit\-Ganzzahl zurück.  Die Funktion gibt \- 1L zurück, um einen Fehler anzugeben.  Wenn sie übergeben werden, ist ein ungültiger Parameter, z ein ungültiger Dateideskriptor oder der Wert für *Ursprung* ungültig, oder die Position, die durch *Offset* angegeben wird, ist, bevor der Anfang der Datei, der ungültige Parameterhandler aufgerufen wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, dieses Features legen Sie `errno` auf `EBADF` und wieder \-1L.  Auf den Geräten, die vom Suchen \(z Anschlüssen und Druckern\) nicht sind, wird der Rückgabewert undefiniert.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Funktion `_lseek` wird der Dateizeiger, der mit `fd` an eine neue Position zugeordnet wird, die *Offsetbytes* *vom Ursprung* ist.  Im folgenden Vorgang in der Datei wird an der neuen Position auf.  Das *Ursprungsargument* muss eine der folgenden Konstanten sein, die in Stdio.h definiert werden.  
  
 `SEEK_SET`  
 Anfang der Datei.  
  
 `SEEK_CUR`  
 Aktuelle Position des Dateizeigers.  
  
 `SEEK_END`  
 Ende der Datei.  
  
 Sie können `_lseek` verwenden, um den Zeiger an jeder Stelle in einer Datei oder im Dateiende hinaus neu anzuordnen.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_lseek`|\<io.h\>|  
|`_lseeki64`|\<io.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_lseek.c  
/* This program first opens a file named lseek.txt.  
 * It then uses _lseek to find the beginning of the file,  
 * to find the current position in the file, and to find  
 * the end of the file.  
 */  
  
#include <io.h>  
#include <fcntl.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh;  
   long pos;               /* Position of file pointer */  
   char buffer[10];  
  
   _sopen_s( &fh, "crt_lseek.c_input", _O_RDONLY, _SH_DENYNO, 0 );  
  
   /* Seek the beginning of the file: */  
   pos = _lseek( fh, 0L, SEEK_SET );  
   if( pos == -1L )  
      perror( "_lseek to beginning failed" );  
   else  
      printf( "Position for beginning of file seek = %ld\n", pos );  
  
   /* Move file pointer a little */  
    _read( fh, buffer, 10 );  
  
   /* Find current position: */  
   pos = _lseek( fh, 0L, SEEK_CUR );  
   if( pos == -1L )  
      perror( "_lseek to current position failed" );  
   else  
      printf( "Position for current position seek = %ld\n", pos );  
  
   /* Set the end of the file: */  
   pos = _lseek( fh, 0L, SEEK_END );  
   if( pos == -1L )  
      perror( "_lseek to end failed" );  
   else  
      printf( "Position for end of file seek = %ld\n", pos );  
  
   _close( fh );  
}  
```  
  
## Eingabe: crt\_lseek.c\_input  
  
```  
Line one.  
Line two.  
Line three.  
Line four.  
Line five.  
```  
  
## Ausgabe  
  
```  
Position for beginning of file seek = 0  
Position for current position seek = 10  
Position for end of file seek = 57  
```  
  
## Siehe auch  
 [E\/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_tell, \_telli64](../../c-runtime-library/reference/tell-telli64.md)