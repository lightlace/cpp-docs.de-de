---
title: "_fgetchar, _fgetwchar"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_fgetchar"
  - "_fgetwchar"
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
  - "fgetwchar"
  - "_fgettchar"
  - "_fgetchar"
  - "_fgetwchar"
  - "fgettchar"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fgetchar-Funktion"
  - "_fgettchar-Funktion"
  - "_fgetwchar-Funktion"
  - "fgetchar-Funktion"
  - "fgettchar-Funktion"
  - "fgetwchar-Funktion"
  - "Standardeingabe, Lesen aus"
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# _fgetchar, _fgetwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest ein Zeichen aus `stdin`.  
  
## Syntax  
  
```  
int _fgetchar( void );  
wint_t _fgetwchar( void );  
```  
  
## Rückgabewert  
 `_fgetchar` gibt das gelesene Zeichen als `int` zurück oder gibt `EOF` zurück, um einen Fehler oder ein Dateiende anzugeben.  **\_**`fgetwchar` gibt als das dem gelesenen Zeichen entsprechende Breitzeichen [wint\_t](../../c-runtime-library/standard-types.md) zurück oder gibt `WEOF` zurück, um einen Fehler oder ein Dateiende anzugeben.  Verwenden Sie für beide Funktionen `feof` oder `ferror`, um zwischen einem Fehler und einer Dateiendebedingung zu unterscheiden.  
  
## Hinweise  
 Diese Funktionen lesen ein einzelnes Zeichen aus `stdin`.  Die Funktion erhöht dann den zugeordneten Dateizeiger \(sofern definiert\), um auf das nächste Zeichen zu zeigen.  Wenn der Stream am Dateiende ist, wird der Dateiende\-Indikator für den Stream festgelegt.  
  
 `_fgetchar` entspricht `fgetc( stdin )`.  Entspricht ebenfalls `getchar`, wird jedoch anstelle einer Funktion und eines Makros nur als Funktion implementiert.  `_fgetwchar` ist die Breitzeichenversion von `_fgetchar`.  
  
 Diese Funktionen sind nicht dem ANSI\-Standard kompatibel.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_fgettchar`|`_fgetchar`|`_fgetchar`|`_fgetwchar`|  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fgetchar`|\<stdio.h\>|  
|`_fgetwchar`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_fgetchar.c  
// This program uses _fgetchar to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[81];  
   int  i, ch;  
  
   // Read in first 80 characters and place them in "buffer":  
   ch = _fgetchar();  
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = _fgetchar();  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
}  
```  
  
  **`Zeile eins. Zeile zwei.`Zeile eins.**  
**Zeile zwei.**   
## .NET Framework-Entsprechung  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)