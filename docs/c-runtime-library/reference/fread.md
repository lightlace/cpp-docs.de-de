---
title: "fread | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fread"
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
  - "fread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Daten [C++], Lesen aus Eingabesteam"
  - "fread-Funktion"
  - "Lesen von Daten [C++], aus Eingabestreams"
  - "Streams [C++], Lesen von Daten aus"
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# fread
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest Daten aus einem Stream.  
  
## Syntax  
  
```  
size_t fread(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für Daten.  
  
 `size`  
 Elementgröße in Bytes.  
  
 `count`  
 Maximale Anzahl zu lesende Elemente.  
  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 `fread` gibt die Anzahl der tatsächlich gelesen vollständigen Elementen zurück, die möglicherweise kleiner sind als `count`, wenn ein Fehler auftritt, oder wenn das Ende der Datei vor erreichendem `count` erreicht wird *.* Verwenden Sie die `feof``ferror` oder Funktion, um einen Lesefehler von einer Dateiende\-Bedingung zu unterscheiden.  Wenn `size` oder `count` 0 ist, gibt `fread` 0 zurück und den Pufferinhalt ist unverändert.  Wenn `stream` oder `buffer` ein NULL\-Zeiger ist, ruft `fread` den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, Sätze `errno` dieser Funktion zu `EINVAL` und zu gibt 0 zurück.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `fread`\-Funktion liest bis `count`\-Elemente von `size` Bytes von der Eingabe `stream` und speichert sie in `buffer`*.* Der Dateizeiger, der `stream` zugeordnet ist \(sofern eines vorhanden ist\), wird durch die Anzahl von Bytes gelesen tatsächlich verbessert.  Wenn der angegebene im Stream Textmodus geöffnet ist, werden Wagenrücklauf\/Zeilenvorschub\-Paare durch einzelne Zeilenvorschubzeichen ersetzt.  Die Ersetzung hat keine Auswirkungen auf der Dateizeiger oder Rückgabewert.  Die Dateizeigerposition ist unbestimmt, wenn ein Fehler auftritt.  Der Wert eines teilweise Leseelements kann nicht bestimmt werden.  
  
 Diese Funktion sperrt out andere Threads.  Wenn Sie eine nicht sperrende Version benötigen, verwenden Sie `_fread_nolock`.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fread`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fread.c  
// This program opens a file named FREAD.OUT and  
// writes 25 characters to the file. It then tries to open  
// FREAD.OUT and read in 25 characters. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   // Open file in text mode:  
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )  
   {  
      for ( i = 0; i < 25; i++ )  
         list[i] = (char)('z' - i);  
      // Write 25 characters to stream   
      numwritten = fwrite( list, sizeof( char ), 25, stream );  
      printf( "Wrote %d items\n", numwritten );  
      fclose( stream );  
  
   }  
   else  
      printf( "Problem opening the file\n" );  
  
   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )  
   {  
      // Attempt to read in 25 characters   
      numread = fread( list, sizeof( char ), 25, stream );  
      printf( "Number of items read = %d\n", numread );  
      printf( "Contents of buffer = %.25s\n", list );  
      fclose( stream );  
   }  
   else  
      printf( "File could not be opened\n" );  
}  
```  
  
  **Umgeschrieben 25 Elemente**  
**Zahl Elemente gelesen \= 25**  
**Inhalt des Puffers \= des zyxwvutsrqponmlkjihgfedcb**   
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [\_read](../../c-runtime-library/reference/read.md)