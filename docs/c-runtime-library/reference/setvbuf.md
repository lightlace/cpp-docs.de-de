---
title: "setvbuf"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "setvbuf"
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
  - "setvbuf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Steuern von Streampufferung"
  - "setvbuf-Funktion"
  - "Streampufferung"
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# setvbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kontrollenstreampufferung und \-Puffergröße.  
  
## Syntax  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
 `buffer`  
 Benutzer\-zugeordneter Puffer.  
  
 `mode`  
 Modus der Pufferung.  
  
 `size`  
 Puffergröße in Bytes.  Zulässiger Bereich: 2 \<\= `size` \<\= INT\_MAX \(2147483647\).  Intern wird der Wert, der für `size` angegebene, unten zur nächsten Vielfachen von 2. gerundet.  
  
## Rückgabewert  
 Gibt bei Erfolg 0 zurück.  
  
 Wenn `stream``NULL` ist oder wenn `mode` oder `size` nicht in einer gültigen Änderung ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, legt gibt diese Funktion \-1 und `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `setvbuf`\-Funktion ermöglicht dem Programm, um Pufferung und Puffergröße für `stream` zu steuern.  `stream` muss eine geöffnete Datei verweisen, die keinen E\/A\-Vorgang unterzogen wurde, seitdem er geöffnet war.  Das Array, auf den durch `buffer` gezeigt wird, wird als Puffer verwendet, es sei denn, dass dies `NULL` ist, in diesem Fall `setvbuf` zugeordneten Puffer einen automatisch der Länge `size`\* \/2 2 Bytes verwendet.  
  
 Der Modus muss `_IOFBF`, `_IOLBF` oder `_IONBF` sein.  Wenn `mode``_IOFBF` oder `_IOLBF` ist, wird `size` wie die Puffergröße verwendet.  Wenn `mode``_IONBF` ist, ist der Stream ungepuffert und `size` und `buffer` ignoriert werden.  Werte für `mode` und ihre Bedeutungen sind:  
  
 `_IOFBF`  
 Vollständige Pufferung; das heißt, wird `buffer` verwendet, während der Puffer und `size` während die Größe des Puffers verwendet wird.  Wenn `buffer``NULL` ist `size`, wird automatisch zugeordnete Bytes eines Puffers lang verwendet.  
  
 `_IOLBF`  
 Für einige Systeme stellt dieses Zeilenpufferung.  Bei Win32, ist das Verhalten dem `_IOFBF` \- full Puffern.  
  
 `_IONBF`  
 Kein Puffer wird, unabhängig von `buffer` oder `size` verwendet.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`setvbuf`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **"stream1" hat jetzt einen Puffer aus 1024 Bytes**  
**"stream2" hat jetzt keinen Puffer**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)