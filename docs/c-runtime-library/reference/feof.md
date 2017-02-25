---
title: "feof | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feof"
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
  - "feof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ende der Datei, Testen auf"
  - "feof-Funktion"
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# feof
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Tests für Dateiende in einem Stream.  
  
## Syntax  
  
```  
int feof(   
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 Die `feof`\-Funktion gibt einen Wert ungleich 0 \(null\) zurück, wenn ein Lesevorgang versucht hat, über das Ende der Datei zu lesen; sie andernfalls gibt 0 zurück.  Wenn der Stream\-Zeiger eine `NULL` ist, wird die Funktion den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno` auf `EINVAL` und die `feof` zurückgibt 0 festgelegt.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Routine `feof` \(implementiert als Funktion und als Makro\) bestimmt, ob das Ende von `stream` übergeben wurde.  Wenn die Datei übergeben wird, geben Lesevorgänge einem Dateiende\-Indikator zurück, bis der Stream geschlossen wird, oder auf `rewind`, `fsetpos`, `fseek` oder `clearerr` für das Element aufgerufen wird.  
  
 Wenn eine Datei 10 Bytes enthält und Sie 10 Bytes aus der Datei lesen, gibt `feof` 0 zurück, da, obwohl der Dateizeiger am Ende der Datei ist, Sie nicht versucht haben, über das Ende hinaus zu lesen.  Erst nach Sie versuchen zu lesen, wird ein 11 Byte. `feof` Rückgabe ein Wert ungleich 0.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`feof`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_feof.c  
// This program uses feof to indicate when  
// it reaches the end of the file CRT_FEOF.TXT. It also  
// checks for errors with ferror.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int  count, total = 0;  
   char buffer[100];  
   FILE *stream;  
  
   fopen_s( &stream, "crt_feof.txt", "r" );  
   if( stream == NULL )  
      exit( 1 );  
  
   // Cycle until end of file reached:  
   while( !feof( stream ) )  
   {  
      // Attempt to read in 100 bytes:  
      count = fread( buffer, sizeof( char ), 100, stream );  
      if( ferror( stream ) )      {  
         perror( "Read error" );  
         break;  
      }  
  
      // Total up actual bytes read  
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   fclose( stream );  
}  
```  
  
## Eingabe: crt\_feof.txt  
  
```  
Line one.  
Line two.  
```  
  
### Ausgabe  
  
```  
Number of bytes read = 19  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)   
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)