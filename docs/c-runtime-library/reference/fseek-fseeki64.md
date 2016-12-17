---
title: "fseek, _fseeki64"
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
  - "_fseeki64"
  - "fseek"
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
apitype: "DLLExport"
f1_keywords: 
  - "fseek"
  - "_fseeki64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fseeki64-Funktion"
  - "Dateizeiger [C++]"
  - "Dateizeiger [C++], Verschieben"
  - "fseek-Funktion"
  - "fseeki64-Funktion"
  - "seek-Dateizeiger"
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# fseek, _fseeki64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verschiebt der Dateizeiger auf einer bestimmten Position.  
  
## Syntax  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
 `offset`  
 Anzahl Bytes von `origin`.  
  
 `origin`  
 Startposition.  
  
## Rückgabewert  
 Wenn erfolgreich, `fseek` und `_fseeki64` gibt 0 zurück.  Andernfalls gibt es einen Wert ungleich 0 \(null\) zurück.  Auf den Geräten, die vom Suchen Unable sind, wird der Rückgabewert undefiniert.  Wenn `stream` ein NULL\-Zeiger ist oder wenn `origin` keine von den unten beschriebenen zulässigen Werten ist, rufen `fseek` und `_fseeki64` den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben – 1 zurück.  
  
## Hinweise  
 `fseek` und `_fseeki64` \- Ablaufverfolgungsfeatures Wechselt der Dateizeiger \(falls vorhanden\) zugeordnet `stream` an eine neue Position, die `offset` Bytes von `origin`*.* Der folgende Operation im Stream wird an der neuen Position stattfindet.  Auf einem Stream, der zur Aktualisierung geöffnet ist, kann der folgende Operation entweder ein Lese\- bzw. eine Schreiboperation sein.  Der Argumentursprung muss eine der folgenden Konstanten sein, die in STDIO.H:  
  
 `SEEK_CUR`  
 Aktuelle Position des Dateizeigers.  
  
 `SEEK_END`  
 Ende der Datei.  
  
 `SEEK_SET`  
 Anfang der Datei.  
  
 Sie können `fseek` und `_fseeki64` verwenden, um den Zeiger an jeder Stelle in einer Datei neu anzuordnen.  Der Zeiger kann über das Dateiende hinausgehen positioniert werden.  `fseek` und `_fseeki64` löscht den Dateiende\-Indikator und neutralisiert die Wirkung aller früheren `ungetc` Aufrufe für `stream`.  
  
 Wenn eine Datei für das Anfügen von Daten geöffnet ist, wird die Position der aktuellen Datei vom letzten E\/A\-Vorgang, nicht davon ab, wo die folgenden auftreten würden schreiben.  Wenn kein E\/A\-Vorgang noch auf eine Datei aufgetreten ist, die zum Anhängen geöffnet ist, ist die Dateiposition der Anfang der Datei.  
  
 Für die Streams, die im Textmodus geöffnet sind, weisen `fseek` und `_fseeki64` konfigurieren Verwendung, da Wagenrücklauf\/Zeilenvorschub\-Übersetzungen `fseek` und `_fseeki64` geben können, unerwartete Ergebnisse zu erzeugen.  Einzige `fseek` und die `_fseeki64`\- Operationen, die gewährleistet werden, um an den Stream zu arbeiten geöffnet sind im Textmodus, sind:  
  
-   Suchen mit einem Offset von 0 in Bezug auf die Ursprungswerte.  
  
-   Suchen der Anfang der Datei mit einen Offsetwert zurückgegeben aus einem Aufruf an `ftell`, wenn `fseek` oder `_ftelli64` verwendet werden, wenn `_fseeki64` verwendet wird.  
  
 Auch im Textmodus, STRG\+Z Dateiendezeichen wird als auf Eingabe interpretiert.  In den Dateien, die für das Lesen und Schreiben geöffnet sind, entfernen `fopen` und alle verwandten Routinenüberprüfung für STRG\+Z am Ende der Datei und sie, sofern möglich.  Dies geschieht, da die Anwendung u der Kombination von `fseek` und `ftell` oder `_fseeki64` und `_ftelli64`, die in einer Datei zu ersetzen, die mit STRG\+Z beendet, `fseek` oder `_fseeki64` bewirkt, dass sie nahe dem Ende der Datei nicht ordnungsgemäß verhält.  
  
 Wenn das CRT eine Datei öffnet, die mit einer Bytereihenfolgemarkierung \(BOM\) beginnt, wird der Dateizeiger nach der BOM positioniert \(das heißt, am Anfang des Inhalts der tatsächlichen Datei\).  Wenn Sie `fseek` an den Anfang der Datei müssen, verwenden Sie `ftell`, die Startposition und `fseek` an es abzurufen, anstatt 0 zu positionieren.  
  
 Diese Funktion sperrt out andere Threads während der Ausführung und daher threadsicher.  Eine nicht sperrende Version finden Sie unter [\_fseek\_nolock, \_fseeki64\_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md).  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fseek`|\<stdio.h\>|  
|`_fseeki64`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
  **Dateizeiger wird auf Mitte der ersten Zeile festgelegt.**  
**Dies ist die Datei "fseek.out".**   
## .NET Framework-Entsprechung  
  
-   [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
-   [System::IO::FileStream::Seek](https://msdn.microsoft.com/en-us/library/system.io.filestream.seek.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)