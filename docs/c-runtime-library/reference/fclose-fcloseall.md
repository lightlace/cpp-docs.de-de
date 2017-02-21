---
title: "fclose, _fcloseall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fclose"
  - "_fcloseall"
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
  - "fclose"
  - "_fcloseall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fclose-Funktion"
  - "Streams, Schließen"
  - "_fcloseall-Funktion"
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# fclose, _fcloseall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Enthält einen Stream \(`fclose`\) oder schließt alle geöffneten Streams \(`_fcloseall`\).  
  
## Syntax  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 `fclose` gibt 0 zurück, wenn der Stream erfolgreich geschlossen wird.  `_fcloseall` gibt die Anzahl der geschlossenen Streams zurück.  Beide Funktionen Rückhol\- `EOF`, um einen Fehler anzugeben.  
  
## Hinweise  
 Die `fclose`\-Funktion enthält die `stream`.  Wenn `stream` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die Ausführung zulässig ist, um fortzufahren, legt `fclose``errno` auf `EINVAL` festgelegt und `EOF` zurückgegeben.  Es wird empfohlen, dass der `stream` Zeiger immer vor dem Aufrufen dieser Funktion überprüft wird.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Die `_fcloseall`\-Funktion schließt alle geöffneten Streams außer `stdin`, `stdout`, `stderr` \(und, in MS\-DOS\-, `_stdaux` und `_stdprn`\).  Sie enthält auch und löscht alle temporären Dateien, die von `tmpfile` erstellt werden.  In beiden Funktionen puffert alles zugeordnetes mit dem Stream werden geleert vor dem Schließen.  System\-zugeordnete Puffer werden freigegeben, wenn der Stream geschlossen wird.  Die Puffer, die vom Benutzer mit `setbuf` und `setvbuf` zugewiesen werden, werden nicht automatisch freigegeben.  
  
 **Note:** , falls diese Funktionen verwendet werden, um einen Stream zu schließen, der zugrunde liegende Dateideskriptor und von Betriebssystemdateihandle \(oder der Socket\) werden sowie der Stream geschlossen.  Wenn die Datei ursprünglich als Dateihandle oder Dateideskriptor geöffnet war und mit `fclose` geschlossen wird, nicht auch rufen Sie `_close` auf, um den Dateideskriptor zu schließen; rufen Sie nicht die Win32\-Funktion `CloseHandle` auf, um das Dateihandle zu schließen.  
  
 `fclose` und für Fehler von anderen Threads an `_fcloseall` Code schützen, variieren.  Für nicht sperrende Version von `fclose`, finden Sie unter `_fclose_nolock`.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fclose`|\<stdio.h\>|  
|`_fcloseall`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::BinaryReader::Close](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.close.aspx)  
  
-   [System::IO::BinaryWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.close.aspx)  
  
-   [System::IO::StringReader::Close](https://msdn.microsoft.com/en-us/library/system.io.stringreader.close.aspx)  
  
-   [System::IO::StringWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.stringwriter.close.aspx)  
  
-   [System::IO::Stream::Close](https://msdn.microsoft.com/en-us/library/system.io.stream.close.aspx)  
  
-   [System::IO::StreamReader::Close](https://msdn.microsoft.com/en-us/library/system.io.streamreader.close.aspx)  
  
-   [System::IO::StreamWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.close.aspx)  
  
-   [System::IO::TextReader::Close](https://msdn.microsoft.com/en-us/library/system.io.textreader.close.aspx)  
  
-   [System::IO::TextWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.textwriter.close.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)