---
title: "fread_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fread_s"
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
  - "fread_s"
  - "stdio/fread_s"
dev_langs: 
  - "C++"
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fread_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest Daten aus einem Stream.  Diese Version von [fread](../../c-runtime-library/reference/fread.md) verfügt werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
size_t fread_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für Daten.  
  
 `bufferSize`  
 Größe des Zielpuffers in Bytes.  
  
 `elementSize`  
 Größe des Elements, um von Bytes in zu lesen.  
  
 `count`  
 Maximale Anzahl zu lesende Elemente.  
  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 `fread_s` gibt die Anzahl der \(ganzen\) Elemente zurück, die in den Puffer gelesen wurden ist, der kleiner als `count` sein, wenn ein Lesefehler oder das Ende der Datei erreicht wird, bevor `count` erreicht wird.  Verwenden Sie die `feof``ferror` oder Funktion, um einen Fehler aus einer Dateiende\-Bedingung zu unterscheiden.  Wenn `size` oder `count` 0 ist, gibt `fread_s` 0 zurück und den Pufferinhalt ist unverändert.  Wenn `stream` oder `buffer` ein NULL\-Zeiger ist, ruft `fread_s` den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, Sätze `errno` dieser Funktion zu `EINVAL` und zu gibt 0 zurück.  
  
 Weitere Informationen zu Fehlercodes, finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `fread_s`\-Funktion liest bis `count`\-Elemente von `elementSize` Bytes von der Eingabe `stream` und speichert sie in `buffer`.  Der Dateizeiger, der `stream` zugeordnet ist \(sofern eines vorhanden ist\), wird durch die Anzahl von Bytes gelesen tatsächlich verbessert.  Wenn der angegebene im Stream Textmodus geöffnet ist, werden Wagenrücklauf\/Zeilenvorschub\-Paare durch einzelne Zeilenvorschubzeichen ersetzt.  Die Ersetzung hat keine Auswirkungen auf der Dateizeiger oder Rückgabewert.  Die Dateizeigerposition ist unbestimmt, wenn ein Fehler auftritt.  Der Wert eines teilweise Leseelements kann nicht bestimmt werden.  
  
 Diese Funktion sperrt out andere Threads.  Wenn Sie eine nicht sperrende Version benötigen, verwenden Sie `_fread_nolock`.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fread_s`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```cpp  
  
// crt_fread_s.c  
// Command line: cl /EHsc /nologo /W4 crt_fread_s.c  
//  
// This program opens a file that's named FREAD.OUT and  
// writes characters to the file. It then tries to open  
// FREAD.OUT and read in characters by using fread_s. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
#define BUFFERSIZE 30  
#define DATASIZE 22  
#define ELEMENTCOUNT 2  
#define ELEMENTSIZE (DATASIZE/ELEMENTCOUNT)  
#define FILENAME "FREAD.OUT"  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   for ( i = 0; i < DATASIZE; i++ )  
      list[i] = (char)('z' - i);  
   list[DATASIZE] = '\0'; // terminal null so we can print it  
  
   // Open file in text mode:  
   if( fopen_s( &stream, FILENAME, "w+t" ) == 0 )  
   {  
      // Write DATASIZE characters to stream   
      printf( "Contents of buffer before write/read:\n\t%s\n\n", list );  
      numwritten = fwrite( list, sizeof( char ), DATASIZE, stream );  
      printf( "Wrote %d items\n\n", numwritten );  
      fclose( stream );  
   } else {  
      printf( "Problem opening the file\n" );  
      return -1;  
   }  
  
   if( fopen_s( &stream, FILENAME, "r+t" ) == 0 )   {  
      // Attempt to read in characters in 2 blocks of 11  
      numread = fread_s( list, BUFFERSIZE, ELEMENTSIZE, ELEMENTCOUNT, stream );  
      printf( "Number of %d-byte elements read = %d\n\n", ELEMENTSIZE, numread );  
      printf( "Contents of buffer after write/read:\n\t%s\n", list );  
      fclose( stream );  
   } else {  
      printf( "File could not be opened\n" );  
      return -1;  
   }  
}  
```  
  
  **Inhalt des Puffers vor schreibt\/gelesen:**   
 **zyxwvutsrqponmlkjihgfe**  
 **Umgeschrieben 22 Elemente**   
 **Zahl von 11 Byteelementen Leseberechtigung \= 2**   
 **Inhalt des Puffers nach schreibt\/gelesen:**   
 **zyxwvutsrqponmlkjihgfe**    
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [\_read](../../c-runtime-library/reference/read.md)