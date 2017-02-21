---
title: "_putw | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putw"
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
  - "_putw"
  - "putw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putw-Funktion"
  - "Ganze Zahlen, Schreiben in Streams"
  - "putw-Funktion"
  - "Streams, Schreiben von ganzen Zahlen in"
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _putw
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt eine ganze Zahl einem Stream.  
  
## Syntax  
  
```  
  
      int _putw(  
   int binint,  
   FILE *stream   
);  
```  
  
#### Parameter  
 *binint*  
 Ausgegeben werden ganze binären Ganzzahlwert.  
  
 `stream`  
 Zeiger zu der **FILE**\-Struktur.  
  
## Rückgabewert  
 Gibt dem geschriebenen Wert zurück.  Bei dem Rückgabewert `EOF` könnte einen Fehler an.  Da `EOF` auch ein legitimer ganzzahliger Wert, mit `ferror`, einen Fehler zu überprüfen.  Wenn `stream` ein NULL\-Zeiger ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt `EOF` zurück.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_putw`\-Funktion wird ein Binärwert des Typs `int` zur aktuellen Position *des Streams.* `_putw` beeinflusst die Ausrichtung von Elementen im Stream noch davon ausgegangen wird keine besondere Ausrichtung.  `_putw` ist hauptsächlich für die Kompatibilität mit früheren Bibliotheken.  Portabilitätsprobleme können sich mit `_putw` auf, weil die Größe von `int` und die Reihenfolge von Bytes innerhalb `int` Systemen zu unterscheiden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_putw`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_putw.c  
/* This program uses _putw to write a  
 * word to a stream, then performs an error check.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   unsigned u;  
   if( fopen_s( &stream, "data.out", "wb" ) )  
      exit( 1 );  
   for( u = 0; u < 10; u++ )  
   {  
      _putw( u + 0x2132, stream );   /* Write word to stream. */  
      if( ferror( stream ) )         /* Make error check. */  
      {  
         printf( "_putw failed" );  
         clearerr_s( stream );  
         exit( 1 );  
      }  
   }  
   printf( "Wrote ten words\n" );  
   fclose( stream );  
}  
```  
  
## Ausgabe  
  
```  
Wrote ten words  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_getw](../../c-runtime-library/reference/getw.md)