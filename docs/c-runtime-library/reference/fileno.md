---
title: "_fileno"
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
  - "_fileno"
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
  - "_fileno"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Dateihandles [C++], Abrufen aus Streams"
  - "fileno-Funktion"
  - "_fileno-Funktion"
  - "Streams, Abrufen von Dateihandles"
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
caps.latest.revision: 19
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# _fileno
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Dateideskriptor ab, der einem Stream zugeordnet ist.  
  
## Syntax  
  
```  
int _fileno(   
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger auf die `FILE`\-Struktur.  
  
## Rückgabewert  
 `_fileno` gibt den Dateideskriptor zurück.  Es gibt keine Fehlerrückgabe.  Das Ergebnis ist nicht, wenn keine `stream` geöffnete Datei angibt.  Wenn Stream `NULL` ist, ruft \_`fileno` den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, legt gibt diese Funktion \-1 und `errno` auf `EINVAL` fest.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
> [!NOTE]
>  Wenn `stdout` oder `stderr` nicht mit einem Ausgabestream, \(beispielsweise in einer Windows\-basierten Anwendung ohne ein Konsolenfenster\) zugeordnet ist, ist der zurückgegebene Dateideskriptor \-2.  In früheren Versionen hieß der zurückgegebene Dateideskriptor \-1.  Diese Änderung ermöglicht Anwendungen, diese Bedingung von einem Fehler zu unterscheiden.  
  
## Hinweise  
 Die Routine `_fileno` gibt den Dateideskriptor zurück, der nur mit `stream` zugeordnet ist.  Diese Routine wird als Funktion und als Makro implementiert.  Weitere Informationen zum Auswählen jeder Implementierung, finden Sie unter [Auswählen zwischen Funktionen und Makros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fileno`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fileno.c  
// This program uses _fileno to obtain  
// the file descriptor for some standard C streams.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );  
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );  
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );  
}  
```  
  
  **Der Dateideskriptor für stdin ist 0**  
**Der Dateideskriptor für stdout ist 1**  
**Der Dateideskriptor für stderr ist 2**   
## .NET Framework-Entsprechung  
 [System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [\_filelength, \_filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)