---
title: "_putc_nolock, _putwc_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putc_nolock"
  - "_putwc_nolock"
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
  - "_puttc_nolock"
  - "puttc_nolock"
  - "putwc_nolock"
  - "_putwc_nolock"
  - "_putc_nolock"
  - "putc_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putc_nolock-Funktion"
  - "_puttc_nolock-Funktion"
  - "_putwc_nolock-Funktion"
  - "Zeichen, Schreiben"
  - "putc_nolock-Funktion"
  - "puttc_nolock-Funktion"
  - "putwc_nolock-Funktion"
  - "Streams, Schreiben von Zeichen in"
ms.assetid: 3cfc7f21-c9e8-4b7f-b0fb-af0d4d85e7e1
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _putc_nolock, _putwc_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt ein Zeichen in einen Stream, ohne den Thread zu sperren.  
  
## Syntax  
  
```  
  
      int _putc_nolock(  
   int c,  
   FILE *stream   
);  
wint_t _putwc_nolock(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### Parameter  
 `c`  
 Zu schreibende Zeichen.  
  
 `stream`  
 Zeiger zu der **FILE**\-Struktur.  
  
## Rückgabewert  
 Siehe **putc, putwc**.  
  
## Hinweise  
 `_putc_nolock` und `_putwc_nolock` sind identisch mit den Versionen ohne das **\_nolock**\-Suffix; allerdings sind sie nicht vor Störungen durch andere Threads geschützt.  Sie sind möglicherweise schneller, da kein Mehraufwand zur Sperrung anderer Threads erforderlich ist.  Verwenden Sie diese Funktionen nur in threadsichere Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen der aufrufende Bereich die Threadisolation bereits handhabt.  
  
 `_putwc_nolock` ist die Breitzeichenversion von `_putc_nolock`; die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI\-Modus geöffnet ist.  `_putc_nolock` unterstützt derzeit die Ausgabe in einen UNICODE\-Stream nicht.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_puttc_nolock`|`_putc_nolock`|`_putc_nolock`|**\_putwc\_nolock**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_putc_nolock`|\<stdio.h\>|  
|`_putwc_nolock`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_putc_nolock.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
   /* Make standard out the stream and write to it. */  
   stream = stdout;  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = _putc_nolock( *p, stream );  
}  
```  
  
## Ausgabe  
  
```  
This is the line of output  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)