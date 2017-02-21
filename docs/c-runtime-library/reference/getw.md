---
title: "getw | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getw"
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
  - "getw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "getw-Funktion"
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _getw
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft eine ganze Zahl aus einem Stream ab.  
  
## Syntax  
  
```  
int _getw(   
   FILE *stream   
);  
```  
  
#### Parameter  
 `stream`  
 Zeiger auf die `FILE`\-Struktur.  
  
## Rückgabewert  
 `_getw` gibt dem Lesen des ganzzahligen Wert zurück.  Bei dem Rückgabewert `EOF` gibt entweder einen Fehler oder eine Datei an.  Da der `EOF`\-Wert auch ein legitimer ganzzahliger Wert, eine mit `feof` oder `ferror`, ein Dateiende oder einen Fehlerzustand zu überprüfen.  Wenn `stream` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `EOF` zurück.  
  
## Hinweise  
 Die `_getw`\-Funktion liest den folgenden Binärwert des Typs `int` aus der Datei, die `stream` zugeordnet wird und erhöht den Zeiger der zugeordneten Datei \(sofern vorhanden\), um den folgenden ungelesenen Zeichen zu veranschaulichen.  `_getw` nimmt keine besondere Ausrichtung von Elementen im Stream.  Probleme mit Portieren `_getw` können auftreten, da die Größe des Typs `int` und die Reihenfolge von Bytes innerhalb des `int`\-Typs über Systemen unterscheiden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_getw`|\<stdio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_getw.c  
// This program uses _getw to read a word  
// from a stream, then performs an error check.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   int i;  
  
   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )  
      printf( "Couldn't open file\n" );  
   else  
   {  
      // Read a word from the stream:  
      i = _getw( stream );  
  
      // If there is an error...  
      if( ferror( stream ) )  
      {  
         printf( "_getw failed\n" );  
         clearerr_s( stream );  
      }  
      else  
         printf( "First data word in file: 0x%.4x\n", i );  
      fclose( stream );  
   }  
}  
```  
  
## Eingabe: crt\_getw.txt  
  
```  
Line one.  
Line two.  
```  
  
### Ausgabe  
  
```  
First data word in file: 0x656e694c  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_putw](../../c-runtime-library/reference/putw.md)