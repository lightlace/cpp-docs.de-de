---
title: "_flushall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_flushall"
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
  - "_flushall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flushall-Funktion"
  - "Leeren von Streams"
  - "Streams, Leeren"
  - "_flushall-Funktion"
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _flushall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Leert alle Streams und löscht alle Puffer.  
  
## Syntax  
  
```  
int _flushall( void );  
```  
  
## Rückgabewert  
 `_flushall` gibt die Anzahl der geöffneten Streams zurück \(Eingaben und Ausgaben\).  Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Standardmäßig schreibt die `_flushall`\-Funktion den Inhalt aller Puffer, die mit geöffneten Ausgabestreams verknüpft sind, in die entsprechenden Dateien.  Aus allen Puffern, die geöffneten Eingabestreams zugeordnet sind, wird der aktuelle Inhalt gelöscht. \(Diese Puffer werden normalerweise vom Betriebssystem verwaltet, das die optimale Zeit zum automatischen Schreiben der Daten auf den Datenträger bestimmt: wenn ein Puffer ist voll, wenn ein Stream geschlossen wird oder wenn ein Programm normal beendet wird, ohne die Streams zu schließen.\)  
  
 Wenn ein Lesevorgang nach einem Aufruf von `_flushall` erfolgt, werden neue Daten aus den Eingabedateien in die Puffer gelesen.  Alle Streams bleiben nach dem Aufruf von `_flushall` geöffnet.  
  
 Mit der Datenträgercommitfunktion der Laufzeitbibliothek können Sie sicherstellen, dass wichtige Daten direkt auf den Datenträger anstatt in die Betriebssystempuffer geschrieben werden.  Sie können diese Funktion aktivieren, ohne ein vorhandenes Programm umzuschreiben. Verknüpfen Sie hierzu die Objektdateien des Programms mit "Commode.obj".  In der resultierenden ausführbaren Datei schreiben Aufrufe von `_flushall` den Inhalt aller Puffer auf den Datenträger.  Nur `_flushall` und `fflush` werden von "Commode.obj" beeinflusst.  
  
 Weitere Informationen zum Steuern der Datenträgercommitfunktion finden Sie unter [Stream\-E\/A](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) und [\_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_flushall`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
  **Es wurden 3 Streams geleert.**   
## .NET Framework-Entsprechung  
  
-   [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
-   [System::IO::StreamWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.flush.aspx)  
  
-   [System::IO::TextWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.textwriter.flush.aspx)  
  
-   [System::IO::BinaryWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.flush.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_commit](../../c-runtime-library/reference/commit.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)