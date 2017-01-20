---
title: "setbuf"
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
  - "setbuf"
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
  - "setbuf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "setbuf-Funktion"
  - "Streampufferung"
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# setbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kontrollenstreampufferung.  Diese Funktion ist veraltet; Verwenden Sie stattdessen [setvbuf](../../c-runtime-library/reference/setvbuf.md).  
  
## Syntax  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
 `buffer`  
 Benutzer\-zugeordneter Puffer.  
  
## Hinweise  
 Die `setbuf`\-Funktion steuert Pufferung für `stream`.  Das `stream`\-Argument muss eine geöffnete Datei verweisen, die nicht gelesen wurde oder geschrieben wurde.  Wenn das Argument `buffer``NULL` ist, ist der Stream ungepuffert.  Wenn nicht, muss der Puffer für ein Zeichenarray der Länge `BUFSIZ` veranschaulichen, in der `BUFSIZ` die Puffergröße ist, wie in STDIO.H. definiert.  Der vom Benutzer angegebene, Puffer anstelle des standardmäßigen System\-zugeordneten Puffers für den jeweiligen Stream, wird für E\/A\-Pufferung verwendet.  Der Stream `stderr` ist standardmäßig ungepuffert, doch Sie können `setbuf` verwenden, um Puffer `stderr` zuzuweisen.  
  
 `setbuf` wurde durch die [setvbuf](../../c-runtime-library/reference/setvbuf.md) ersetzt, das die bevorzugte Routine für neuen Code ist.  `setbuf` wird für die Kompatibilität mit vorhandenem Code beibehalten.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`setbuf`|\<stdio.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **stream1 festgelegt auf benutzerdefinierten Puffer an: 0012FCDC**  
**Pufferung stream2 deaktiviert**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)