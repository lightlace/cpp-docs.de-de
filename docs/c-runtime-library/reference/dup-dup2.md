---
title: "_dup, _dup2"
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
  - "_dup"
  - "_dup2"
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
  - "_dup2"
  - "_dup"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_dup-Funktion"
  - "_dup2-Funktion"
  - "dup-Funktion"
  - "dup2-Funktion"
  - "Dateihandles [C++], Duplizieren"
  - "Dateihandles [C++], Neuzuweisen"
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: 19
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# _dup, _dup2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt einen zweiten Dateideskriptor für eine geöffnete Datei \(`_dup`\) oder weist einen Dateideskriptor neu zu \(`_dup2`\).  
  
## Syntax  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### Parameter  
 `fd`, `fd1`  
 Dateideskriptoren, die auf die geöffnete Datei verweisen.  
  
 `fd2`  
 Jeder beliebige Dateideskriptor.  
  
## Rückgabewert  
 `_dup` gibt einen neuen Dateideskriptor zurück.  `_dup2` gibt bei Erfolg 0 zurück.  Wenn ein Fehler auftritt, gibt jede Funktion – 1 zurück und legt bei einem ungültigen Dateideskriptor `errno` auf `EBADF` fest oder auf `EMFILE`, wenn keine weiteren Dateideskriptoren verfügbar sind.  Bei einem ungültigen Dateideskriptor ruft die Funktion auch den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Funktionen `_dup` und `_dup2` ordnen einen zweiten Dateideskriptor einer momentan geöffneten Datei zu.  Diese Funktionen können verwendet werden, um einen vordefinierten Dateideskriptor – wie z. B. `stdout` – einer anderen Datei zuzuordnen.  Das Durchführen von Operationen an der Datei ist mit jedem der beiden Dateideskriptoren möglich.  Der für die Datei zulässige Zugriffstyp ist von der Erstellung eines neuen Deskriptors nicht betroffen.  `_dup` gibt den nächsten verfügbaren Dateideskriptor für die angegebene Datei zurück.  `_dup2` erzwingt `fd2`, um auf dieselbe Datei wie `fd1` zu verweisen.  Wenn `fd2` zum Zeitpunkt des Aufrufs einer geöffneten Datei zugeordnet ist, wird diese Datei geschlossen.  
  
 `_dup` und `_dup2` akzeptieren Dateideskriptoren als Parameter.  Um einen Stream `(FILE *)` an jede dieser Funktionen zu übergeben, verwenden Sie [\_fileno](../../c-runtime-library/reference/fileno.md).  Die `fileno`\-Routine gibt den Dateideskriptor zurück, der derzeit dem angegebenen Stream zugeordnet ist.  Das folgende Beispiel zeigt, wie `stderr` \(definiert als `FILE` `*` in Stdio.h\) einem Dateideskriptor zugeordnet wird:  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_dup`|\<io.h\>|  
|`_dup2`|\<io.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_dup.c  
// This program uses the variable old to save  
// the original stdout. It then opens a new file named  
// DataFile and forces stdout to refer to it. Finally, it  
// restores stdout to its original state.  
//  
  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int old;  
   FILE *DataFile;  
  
   old = _dup( 1 );   // "old" now refers to "stdout"   
                      // Note:  file descriptor 1 == "stdout"   
   if( old == -1 )  
   {  
      perror( "_dup( 1 ) failure" );  
      exit( 1 );  
   }  
   _write( old, "This goes to stdout first\n", 26 );  
   if( fopen_s( &DataFile, "data", "w" ) != 0 )  
   {  
      puts( "Can't open file 'data'\n" );  
      exit( 1 );  
   }  
  
   // stdout now refers to file "data"   
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )  
   {  
      perror( "Can't _dup2 stdout" );  
      exit( 1 );  
   }  
   puts( "This goes to file 'data'\n" );  
  
   // Flush stdout stream buffer so it goes to correct file   
   fflush( stdout );  
   fclose( DataFile );  
  
   // Restore original stdout   
   _dup2( old, 1 );  
   puts( "This goes to stdout\n" );  
   puts( "The file 'data' contains:" );  
   _flushall();  
   system( "type data" );  
}  
```  
  
  **This goes to stdout first**  
**This goes to stdout**  
**The file 'data' contains:**  
**This goes to file 'data'**   
## Siehe auch  
 [E\/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)