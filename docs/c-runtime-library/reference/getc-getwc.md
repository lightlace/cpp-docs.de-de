---
title: "getc, getwc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "getwc"
  - "getc"
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
  - "_gettc"
  - "getwc"
  - "_gettchar"
  - "getc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_gettc-Funktion"
  - "Zeichen, Lesen"
  - "getc-Funktion"
  - "gettc-Funktion"
  - "getwc-Funktion"
  - "getwchar-Funktion"
  - "Lesen von Zeichen aus Streams"
  - "Streams, Lesen von Zeichen aus"
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# getc, getwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lesen Sie ein Zeichen von einem Stream.  
  
## Syntax  
  
```  
int getc(   
   FILE *stream   
);  
wint_t getwc(   
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Eingabestream.  
  
## Rückgabewert  
 Gibt das gelesene Zeichen zurück.  So einem Lesefehler oder eine Dateiende\-Bedingung, `getc` gibt `EOF` und `getwc` gibt `WEOF` angeben.  Verwenden Sie für `getc``ferror` oder `feof` zur Fehler\- oder Dateiendeüberprüfung.  Wenn `stream``NULL` ist, rufen `getc` und `getwc` den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, diese Funktionen Rückhol\- `EOF` \(oder `WEOF` für `getwc`\) und `errno` auf `EINVAL` festlegen.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Jede Routine liest ein einzelnes Zeichen aus einer Datei an der aktuellen Position und erhöht den Zeiger der zugeordneten Datei \(wenn Sie definiert werden\), um auf dem nächsten Zeichen zu veranschaulichen.  Die Datei wird `stream` zugeordnet.  
  
 Diese Funktionen sperren den aufrufenden Thread und sind daher threadsicher.  Eine nicht sperrende Version finden Sie unter [\_getc\_nolock, \_getwc\_nolock](../../c-runtime-library/reference/getc-nolock-getwc-nolock.md).  
  
 Es folgen routinespezifische Hinweise.  
  
|Routine|Hinweise|  
|-------------|--------------|  
|`getc`|Identisch mit `fgetc`, implementiert jedoch als Funktion und als Makro.|  
|`getwc`|Breitzeichenversion von `getc`.  Liest ein Mehrbytezeichen oder ein Breitzeichen, ob `stream` im Textmodus oder im Binärdateimodus geöffnet ist.|  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_gettc`|`getc`|`getc`|`getwc`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`getc`|\<stdio.h\>|  
|`getwc`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_getc.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc.txt".   
  
    fopen_s(&fp, "crt_getc.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc.txt.\n");  
       exit(1);  
    }  
  
    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
  
    fclose(fp);  
}  
```  
  
## Eingabe: crt\_getc.txt  
  
```  
Line one.  
Line two.  
```  
  
### Ausgabe  
  
```  
Input was: Line one.  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)