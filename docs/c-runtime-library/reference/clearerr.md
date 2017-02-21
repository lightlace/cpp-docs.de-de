---
title: "clearerr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clearerr"
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
  - "clearerr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clearerr-Funktion"
  - "Fehlerindikator für Streams"
  - "Neufestlegen von Streamfehlerindikator"
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# clearerr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Setzt den Fehler für einen Stream zurück.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [clearerr\_s](../../c-runtime-library/reference/clearerr-s.md).  
  
## Syntax  
  
```  
void clearerr(  
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Hinweise  
 Die `clearerr`\-Funktion setzt den Fehler und den Dateiende\-Indikator für `stream` zurück.  Fehlerindikatoren werden nicht automatisch gelöscht; einmal wird der Fehler für den jeweiligen Stream festgelegt, fahren Vorgänge auf diesem Stream fort, um einem Fehlerwert bis `clearerr`, `fseek`, `fsetpos` zurückzugeben, oder `rewind` wird aufgerufen.  
  
 Wenn `stream` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die Ausführung zulässig ist, um fortzufahren, Sätze `errno` dieser Funktion in `EINVAL` und gibt an.  Weitere Informationen über `errno` und Fehlercodes, finden Sie unter [errno Konstanten](../../c-runtime-library/errno-constants.md).  
  
 Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [clearerr\_s](../../c-runtime-library/reference/clearerr-s.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`clearerr`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_clearerr.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      clearerr( stdin );  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      clearerr( stdin );  
   }  
   else  
      printf( "No read error\n" );  
}  
```  
  
  **`nnWrite` Fehler: Kein Fehler**  
**Bewirkt Eingabe einen Fehler? n**  
**Kein Lesefehler**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)   
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)