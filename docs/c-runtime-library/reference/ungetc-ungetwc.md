---
title: "ungetc, ungetwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ungetwc"
  - "ungetc"
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
  - "_ungettc"
  - "ungetwc"
  - "ungetc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ungettc-Funktion"
  - "Zeichen, zurück auf den Stream"
  - "ungetc-Funktion"
  - "ungettc-Funktion"
  - "ungetwc-Funktion"
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# ungetc, ungetwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schiebt ein Zeichen zurück auf den Stream.  
  
## Syntax  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### Parameter  
 `c`  
 Zu verschiebendes Zeichen.  
  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 Bei Erfolg gibt jede dieser Funktionen das Zeichenargument `c` *zurück.* Wenn `c` nicht zurückgeschoben werden kann oder wenn kein Zeichen gelesen wurde, bleibt der Eingabestream unverändert und `ungetc` gibt `EOF` zurück. `ungetwc` gibt `WEOF` zurück.  Wenn `stream` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, wird `EOF` oder `WEOF` zurückgegeben und `errno` auf `EINVAL` festgelegt.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `ungetc`\-Funktion schiebt das Zeichen `c` wieder auf `stream` und löscht den Dateiendeindikator.  Der Stream muss zum Lesen geöffnet sein.  Ein späterer Lesevorgang auf `stream` beginnt mit `c`*.* Ein Versuch, `EOF` mit `ungetc` auf den Stream zu schieben, wird ignoriert.  
  
 Zeichen, die durch `ungetc` auf dem Stream platziert wurden, werden möglicherweise gelöscht, wenn `fflush`, `fseek`, `fsetpos` oder `rewind` aufgerufen wird, bevor das Zeichen vom Stream gelesen wird.  Der Dateipositionszeiger erhält den Wert, den er auch schon hatte, bevor die Zeichen zurückgeschoben wurden.  Der dem Stream entsprechende externe Speicher ist unverändert.  Bei einem erfolgreichen `ungetc`\-Aufruf für einen Textstream bleibt der Dateipositionszeiger so lange nicht angegeben, bis alle zurückgeschobenen Zeichen gelesen oder verworfen wurden.  Bei jedem erfolgreichen `ungetc`\-Aufruf für einen Binärstream wird der Dateipositionszeiger verringert. War sein Wert vor einem Aufruf 0 \(null\), ist er nach dem Aufruf nicht definiert.  
  
 Ergebnisse sind unvorhersehbar, wenn `ungetc` zwischen den beiden Aufrufen zweimal ohne einen Lesevorgang oder einen Dateipositionierungsvorgang aufgerufen wird.  Nach einem Aufruf von `fscanf` kann ein Aufruf von `ungetc` fehlschlagen, solange kein anderer Lesevorgang \(wie `getc`\) ausgeführt wird.  Der Grund hierfür ist, dass `fscanf` selbst `ungetc` aufruft.  
  
 `ungetwc` ist eine Breitzeichenversion von `ungetc`.  Bei jedem erfolgreichen `ungetwc`\-Aufruf für einen Textstream oder Binärstream bleibt der Dateipositionszeiger jedoch so lange nicht angegeben, bis alle zurückgeschobenen Zeichen gelesen oder verworfen wurden.  
  
 Diese Funktionen sind während der Ausführung threadsichere und sperrabhängige Daten.  Eine nicht sperrende Version finden Sie unter [\_ungetc\_nolock, \_ungetwc\_nolock](../../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`ungetc`|\<stdio.h\>|  
|`ungetwc`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
  **`521a`Zahl \= 521**  
**Nächstes Zeichen im Stream \= "a"**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)