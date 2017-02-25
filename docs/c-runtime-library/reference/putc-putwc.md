---
title: "putc, putwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "putwc"
  - "putc"
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
  - "_puttc"
  - "putwc"
  - "putc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_puttc-Funktion"
  - "Zeichen, Schreiben"
  - "putc-Funktion"
  - "puttc-Funktion"
  - "putwc-Funktion"
  - "Streams, Schreiben von Zeichen in"
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# putc, putwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt ein Zeichen in einen Stream.  
  
## Syntax  
  
```  
  
      int putc(  
   int c,  
   FILE *stream   
);  
wint_t putwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### Parameter  
 `c`  
 Zu schreibende Zeichen.  
  
 `stream`  
 Zeiger auf die **FILE**\-Struktur.  
  
## Rückgabewert  
 Gibt das geschriebene Zeichen zurück.  Um einen Fehler oder eine Dateiendebedingung anzugeben, geben `putc` und `putchar``EOF` zurück; `putwc` und `putwchar` geben **WEOF** zurück.  Verwenden Sie bei allen vier Routinen [ferror](../../c-runtime-library/reference/ferror.md) oder [feof](../../c-runtime-library/reference/feof.md), um auf einen Fehler oder ein Dateiende zu prüfen.  Wenn ein NULL\-Zeiger für `stream` übergeben wird, wird der Handler für ungültige Parameter aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EOF` oder **WEOF** zurück und stellen `errno` auf `EINVAL` ein.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `putc`\-Routine schreibt das einzelne Zeichen `c` in die aktuelle Position der `stream`\-Ausgabe.  Jede beliebige ganze Zahl kann an `putc` übergeben werden, aber es werden nur die unteren 8 Bits geschrieben.  Die `putchar`\-Routine ist mit **putc\(** `c`**,stdout \)** identisch.  Wenn ein Lesefehler auftritt, wird für jede Routine die Fehleranzeige für den Stream festgelegt.  `putc` und `putchar` ähneln jeweils `fputc` und `_fputchar`, werden jedoch sowohl als Funktionen als auch als Makros implementiert \(siehe [Auswählen zwischen Funktionen und Makros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)\).  `putwc` und `putwchar` sind jeweils Breitzeichenversionen von `putc` und `putchar`.  `putwc` und `putc` verhalten sich identisch, wenn der Stream in ANSI\-Modus geöffnet ist.  `putc` unterstützt derzeit die Ausgabe in einen UNICODE\-Stream nicht.  
  
 Die Versionen mit dem Suffix **\_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt.  Weitere Informationen finden Sie unter **\_putc\_nolock, \_putwc\_nolock**.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`putc`|\<stdio.h\>|  
|`putwc`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_putc.c  
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
      ch = putc( *p, stream );  
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