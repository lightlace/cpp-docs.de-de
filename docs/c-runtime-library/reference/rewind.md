---
title: "rewind | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "rewind"
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
  - "rewind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dateizeiger [C++]"
  - "Dateizeiger [C++], Neupositionieren"
  - "Neupositionieren von Dateizeigern"
  - "rewind-Funktion"
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# rewind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ordnet der Dateizeiger am Beginn einer Datei neu.  
  
## Syntax  
  
```  
  
      void rewind(  
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger auf die **FILE**\-Struktur.  
  
## Hinweise  
 Die **rewind**\-Funktion ordnet der Dateizeiger neu mit `stream` am Anfang der Datei zugeordnet ist.  Ein Aufruf **rewind** entspricht ähnelt  
  
 **\(void\) fseek\(** `stream`**, 0L,** `SEEK_SET` **\);**  
  
 jedoch, außer `fseek`, werden **rewind** die Fehlerindikatoren für den Stream und der Dateiende\-Indikator.  Auch als `fseek`, gibt **rewind** keinen Wert zurück, um anzugeben, ob der Zeiger erfolgreich verschoben wurde.  
  
 Die Tastaturpuffer löschen, verwenden Sie **rewind** mit dem Stream `stdin`, der mit der Tastatur standardmäßig zugeordnet ist.  
  
 Wenn ein Stream `NULL` Zeiger ist, ist der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren wird, gibt dieser Funktion und `errno` auf `EINVAL` festgelegt.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**Rückspulen**|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_rewind.c  
/* This program first opens a file named  
 * crt_rewind.out for input and output and writes two  
 * integers to the file. Next, it uses rewind to  
 * reposition the file pointer to the beginning of  
 * the file and reads the data back in.  
 */  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int data1, data2;  
  
   data1 = 1;  
   data2 = -37;  
  
   fopen_s( &stream, "crt_rewind.out", "w+" );  
   if( stream != NULL )  
   {  
      fprintf( stream, "%d %d", data1, data2 );  
      printf( "The values written are: %d and %d\n", data1, data2 );  
      rewind( stream );  
      fscanf_s( stream, "%d %d", &data1, &data2 );  
      printf( "The values read are: %d and %d\n", data1, data2 );  
      fclose( stream );  
   }  
}  
```  
  
## Ausgabe  
  
```  
The values written are: 1 and -37  
The values read are: 1 and -37  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)