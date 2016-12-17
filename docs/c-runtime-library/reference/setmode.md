---
title: "_setmode"
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
  - "_setmode"
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
  - "_setmode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmode-Funktion"
  - "Dateiübersetzung [C++], Festlegen des Modus"
  - "Dateien [C++], Modi"
  - "Dateien [C++], Verschiebung"
  - "setmode-Funktion"
  - "Unicode [C++], Konsolenausgabe"
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
caps.latest.revision: 23
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# _setmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt den Dateiübersetzungsmodus fest.  
  
## Syntax  
  
```  
int _setmode (    int fd,    int mode  );  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor.  
  
 `mode`  
 Neuer Übersetzungsmodus.  
  
## Rückgabewert  
 Im Erfolgsfall wird der vorherige Übersetzungsmodus zurückgegeben.  
  
 Wenn ungültige Parameter an diese Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion –1 zurück und setzt `errno` auf `EBADF`, wodurch ein ungültiger Dateideskriptor angezeigt wird, oder auf `EINVAL`, wodurch ein ungültiges `mode`\-Argument angezeigt wird.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Funktion `_setmode` setzt den Übersetzungsmodus der von `fd` bereitgestellten Datei auf `mode`.  Durch die Übergabe von `_O_TEXT` als `mode` wird der Modus für den übersetzten Text festgelegt.  Kombinationen aus Wagenrücklauf und Zeilenvorschub \(CR\-LF\) werden bei der Eingabe in ein einzelnes Zeilenvorschubzeichen umgewandelt.  Zeilenvorschubzeichen werden bei der Ausgabe in Kombinationen aus Wagenrücklauf und Zeilenvorschub \(CR\-LF\) übersetzt.  Durch die Übergabe von `_O_BINARY` wird der binäre \(nicht übersetzte\) Modus festgelegt, in dem diese Übersetzungen unterdrückt werden.  
  
 Sie können auch `_O_U16TEXT`, `_O_U8TEXT` oder \_`O_WTEXT` übergeben, um den Unicode\-Modus zu aktivieren, wie später im zweiten Beispiel in diesem Dokument demonstriert wird.  `_setmode` wird normalerweise verwendet, um den Standardübersetzungsmodus von `stdin` und `stdout` zu ändern, aber Sie können es für jede Datei verwenden.  Wenn Sie `_setmode` auf den Dateideskriptor für einen Stream anwenden, rufen Sie `_setmode` auf, bevor Sie Eingabe\- oder Ausgabevorgänge an diesem Stream durchführen.  
  
> [!CAUTION]
>  Wenn Sie Daten in einen Dateienstream schreiben, leeren Sie den Code explizit, indem Sie [fflush](../../c-runtime-library/reference/fflush.md) verwenden, bevor Sie `_setmode` verwenden, um den Modus zu ändern.  Wenn Sie den Code nicht leeren, kann es zu unerwartetem Verhalten kommen.  Wenn Sie keine Daten in den Stream geschrieben haben, müssen Sie den Code nicht leeren.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`_setmode`|\<io.h\>|\<fcntl.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_setmode.c  
// This program uses _setmode to change  
// stdin from text mode to binary mode.  
  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
int main( void )  
{  
   int result;  
  
   // Set "stdin" to have binary mode:  
   result = _setmode( _fileno( stdin ), _O_BINARY );  
   if( result == -1 )  
      perror( "Cannot set mode" );  
   else  
      printf( "'stdin' successfully changed to binary mode\n" );  
}  
```  
  
  **'stdin' erfolgreich in Binärmodus geändert**   
## Beispiel  
  
```  
// crt_setmodeunicode.c  
// This program uses _setmode to change  
// stdout to Unicode. Cyrillic and Ideographic  
// characters will appear on the console (if  
// your console font supports those character sets).  
  
#include <fcntl.h>  
#include <io.h>  
#include <stdio.h>  
  
int main(void) {  
    _setmode(_fileno(stdout), _O_U16TEXT);  
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");  
    return 0;  
}  
  
```  
  
## Entsprechung in .NET Framework  
  
-   [\<caps:sentence id\="tgt28" sentenceid\="fe03c471a7a38d5378cea62467482dae" class\="tgtSentence"\>System::IO::BinaryReader Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx)  
  
-   [\<caps:sentence id\="tgt29" sentenceid\="105e62b7505c25e3e182779c87f145eb" class\="tgtSentence"\>System::IO::TextReader Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)