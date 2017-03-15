---
title: "fgetc, fgetwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fgetwc"
  - "fgetc"
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
  - "_fgettc"
  - "fgetwc"
  - "fgetc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fgettc-Funktion"
  - "Zeichen, Lesen"
  - "fgetc-Funktion"
  - "fgettc-Funktion"
  - "fgetwc-Funktion"
  - "Lesen von Zeichen aus Streams"
  - "Streams, Lesen von Zeichen aus"
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# fgetc, fgetwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lesen Sie ein Zeichen von einem Stream.  
  
## Syntax  
  
```  
int fgetc(   
   FILE *stream   
);  
wint_t fgetwc(   
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 `fgetc` gibt das Zeichen zurück, das als `int` gelesen wird oder gibt `EOF`, um einen Fehler anzugeben oder Dateiende zurück.  `fgetwc` gibt, als [wint\_t](../../c-runtime-library/standard-types.md), dem Breitzeichen zurück, das auf Zeichen gelesen oder `WEOF` zurückgibt, um einen Fehler anzugeben oder Dateiende entspricht.  Verwenden Sie für beide Funktionen `feof` oder `ferror`, um zwischen einem Fehler und einer Dateiendebedingung zu unterscheiden.  Wenn ein Lesefehler auftritt, wird der Fehler für den Stream festgelegt.  Wenn `stream``NULL` ist, rufen `fgetc` und `fgetwc` den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EOF` zurück.  
  
## Hinweise  
 Jede dieser Funktionen liest ein einzelnes Zeichen von der aktuellen Position der Datei, die `stream` zugeordnet ist.  Die Funktion erhöht dann den zugeordneten Dateizeiger \(sofern definiert\), um auf das nächste Zeichen zu zeigen.  Wenn der Stream am Dateiende ist, wird der Dateiende\-Indikator für den Stream festgelegt.  
  
 `fgetc` entspricht `getc`, jedoch wird nur als Funktion, sondern als Funktion und Makro implementiert.  
  
 `fgetwc` ist die Breitzeichen\-Version von `fgetc`; `c` liest sie als Mehrbytezeichen oder Breitzeichen, ob `stream` im Textmodus oder im Binärdateimodus geöffnet ist.  
  
 Die Versionen mit dem `_nolock`\-Suffix sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt.  
  
 Weitere Informationen über die Verarbeitung von Breitzeichen und von Mehrbytezeichen in den Text\- und Binärdateimodi, finden Sie unter [Unicode\-Stream E\/A in den Text Binärdatei\-Modi](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_fgettc`|`fgetc`|`fgetc`|`fgetwc`|  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fgetc`|\<stdio.h\>|  
|`fgetwc`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fgetc.c  
// This program uses getc to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   char buffer[81];  
   int  i, ch;  
  
   // Open file to read line from:  
   fopen_s( &stream, "crt_fgetc.txt", "r" );  
   if( stream == NULL )  
      exit( 0 );  
  
   // Read in first 80 characters and place them in "buffer":   
   ch = fgetc( stream );  
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = fgetc( stream );  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
   fclose( stream );  
}  
```  
  
## Eingabe: crt\_fgetc.txt  
  
```  
Line one.  
Line two.  
```  
  
### Ausgabe  
  
```  
Line one.  
Line two.  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)