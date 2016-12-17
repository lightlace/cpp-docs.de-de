---
title: "getchar, getwchar"
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
  - "getchar"
  - "getwchar"
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
  - "getwchar"
  - "GetChar"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_gettchar-Funktion"
  - "Zeichen, Lesen"
  - "gettchar-Funktion"
  - "getwchar-Funktion"
  - "Standardeingabe, Lesen aus"
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# getchar, getwchar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest ein Zeichen aus der Standardeingabe.  
  
## Syntax  
  
```  
int getchar();  
wint_t getwchar();  
```  
  
## Rückgabewert  
 Gibt das gelesene Zeichen zurück.  So einem Lesefehler oder eine Dateiende\-Bedingung, `getchar``returns EOF` und `getwchar` gibt `WEOF` angeben.  Verwenden Sie für `getchar``ferror` oder `feof` zur Fehler\- oder Dateiendeüberprüfung.  
  
## Hinweise  
 Jede Routine liest ein einzelnes Zeichen aus `stdin` und erhöht den zugeordneten Dateizeiger, um auf das nächste Zeichen zu zeigen.  `getchar` entspricht [\_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md), ist jedoch als Funktion und Makro implementiert.  
  
 Diese Funktionen sperren den aufrufenden Thread und sind daher threadsicher.  Eine nicht sperrende Version finden Sie unter [\_getchar\_nolock, \_getwchar\_nolock](../../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_gettchar`|`getchar`|`getchar`|`getwchar`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`getchar`|\<stdio.h\>|  
|`getwchar`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_getchar.c  
// Use getchar to read a line from stdin.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
  
    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
}  
```  
  
  **`Diese Text`\-Eingabe lautete: This text**   
## .NET Framework-Entsprechung  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)