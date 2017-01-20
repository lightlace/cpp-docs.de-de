---
title: "ftell, _ftelli64"
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
  - "_ftelli64"
  - "ftell"
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
  - "_ftelli64"
  - "ftell"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftelli64-Funktion"
  - "Dateizeiger [C++]"
  - "Dateizeiger [C++], Abrufen der aktuellen Position"
  - "ftell-Funktion"
  - "ftelli64-Funktion"
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: 19
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# ftell, _ftelli64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die aktuelle Position eines Dateizeigers ab.  
  
## Syntax  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Ziel `FILE`\-Struktur.  
  
## Rückgabewert  
 `ftell` und `_ftelli64` geben die Position der aktuellen Datei zurück.  Der Wert, der von `ftell` und von `_ftelli64` zurückgegeben wird, spiegelt möglicherweise nicht dem physischen Byteoffset für die Streams, die im Textmodus geöffnet sind, da Wagenrücklauf\/Zeilenvorschub\-Übersetzung Textmodus verursacht.  Verwenden Sie `ftell` mit `fseek` oder `_ftelli64` mit `_fseeki64`, zu Stellen ordnungsgemäß zurückzukehren.  Auf Fehler rufen `ftell` und `_ftelli64` den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, geben diese Funktionen \- 1L und festgelegtem `errno` auf einen von zwei Konstanten zurück, die in ERRNO.H.  Die Konstante `EBADF` bedeutet, dass das Argument `stream` kein gültiger Dateizeigerwert ist oder keine offenen Dateien verweist.  `EINVAL` bedeutet, dass `stream` ein ungültiges Argument an die Funktion übergeben wurde.  Auf den Geräten, die vom Suchen \(z Anschlüssen und Druckern\) oder nicht sind, wenn `stream` verweist keine offenen Dateien, wird der Rückgabewert undefiniert.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `ftell` und `_ftelli64` rufen Funktionen der aktuellen Position des Dateizeigers \(falls vorhanden\) zugeordnet `stream`*ab.* Die Position wird als Offset relativ zum Anfang des Streams ausgedrückt.  
  
 Beachten Sie, dass, wenn eine Datei zum Anfügen von Daten geöffnet ist, die Position der aktuellen Datei vom letzten E\/A\-Vorgang bestimmt wird, nicht durch, wobei die folgenden auftreten würden schreiben.  Wenn eine Datei für ein Angefügte geöffnet und dem letzten Vorgang ein Lese\- war, ist die Dateiposition der Punkt, an dem der Lesevorgang folgenden starten würde nicht schreiben, wobei die folgenden, würde starten. \(Wenn eine Datei zum Anhängen geöffnet ist, wird die Dateiposition auf Dateiende vor jedem Schreibvorgänge\) verschoben. Wenn kein E\/A\-Vorgang noch auf eine Datei aufgetreten ist, die zum Anhängen geöffnet ist, ist die Dateiposition der Anfang der Datei.  
  
 Im Textmodus wird STRG\+Z als Dateiendezeichen auf Eingabe interpretiert.  In den Dateien, die für das Lesen und Schreiben geöffnet sind, entfernen `fopen` und alle verwandten Routinenüberprüfung für STRG\+Z am Ende der Datei und sie, sofern möglich.  Dies geschieht, da die Anwendung u der Kombination von `ftell` und `fseek` oder `_ftelli64` und `_fseeki64`, die in einer Datei zu ersetzen, die mit STRG\+Z beendet, `ftell` oder `_ftelli64` bewirkt, dass sie nahe dem Ende der Datei nicht ordnungsgemäß verhält.  
  
 Diese Funktion sperrt den aufrufenden Thread während der Ausführung und daher threadsicher.  Eine nicht sperrende Version finden Sie unter `_ftell_nolock`.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|Optionale Header|  
|--------------|---------------------------|----------------------|  
|`ftell`|\<stdio.h\>|\<errno.h\>|  
|`_ftelli64`|\<stdio.h\>|\<errno.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
  **Positionieren Sie, nachdem Sie versucht haben, 100 Bytes zu lesen: 100**   
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)