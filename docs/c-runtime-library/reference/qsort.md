---
title: "qsort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "qsort"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "qsort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "qsort-Funktion"
  - "Schnellsortierungsalgorithmus"
  - "Sortieren von Arrays"
  - "Arrays [CRT], Sortieren"
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# qsort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt eine schnelle Sortierung aus.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [qsort\_s](../../c-runtime-library/reference/qsort-s.md).  
  
## Syntax  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### Parameter  
 `base`  
 Anfang des Zielarrays.  
  
 `num`  
 Arraygröße in Elementen.  
  
 `width`  
 Elementgröße in Bytes.  
  
 `compare`  
 Zeiger zu einer vom Benutzer bereitgestellten Routine, die zwei Arrayelemente verglichen und einen Wert zurückgibt, der die Beziehung angibt.  
  
## Hinweise  
 Die `qsort`\-Funktion implementiert einen QuickSortierungsalgorithmus, um ein Array, `num`\-Elemente jedes von `width` Bytes zu sortieren.  Das Argument `base` ist ein Zeiger zur Basis des zu sortierende Arrays.  `qsort` überschreibt dieses Array, indem die sortierten Elemente verwendet.  
  
 `qsort` ruft die Routine `compare` mindestens einmal bei der Sortierung auf und übergibt Zeiger zu zwei Arrayelementen auf jedem Aufruf.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 Die Routine vergleicht die Elemente und gibt einen der folgenden Werte zurück.  
  
|Compare\-Funktions\-Rückgabewert|**Beschreibung**|  
|--------------------------------------|----------------------|  
|\< 0|`elem1` kleiner als `elem2`|  
|0|`elem1` entspricht `elem2`|  
|\> 0|`elem1` größer als `elem2`|  
  
 Das Array ist in aufsteigender Reihenfolge sortiert, wie von der Vergleichsfunktion definiert.  Um ein Array in absteigender Reihenfolge zu sortieren, kehren Sie dem Sinne "in größerem als" und "kleiner als" in der Vergleichsfunktion um.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `compare` oder `num` ist `NULL` oder `base` und `NULL` ist \*`num` ist ungleich 0 \(null\), oder, wenn `width` kleiner als null ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, kehrt die Funktion zurück und `errno` ist auf `EINVAL` festgelegt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`qsort`|\<stdlib.h und\> search.h \<\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_qsort.c  
// arguments: every good boy deserves favor  
  
/* This program reads the command-line  
 * parameters and uses qsort to sort them. It  
 * then displays the sorted arguments.  
 */  
  
#include <stdlib.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main( int argc, char **argv )  
{  
   int i;  
   /* Eliminate argv[0] from sort: */  
   argv++;  
   argc--;  
  
   /* Sort remaining args using Quicksort algorithm: */  
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );  
  
   /* Output sorted list: */  
   for( i = 0; i < argc; ++i )  
      printf( " %s", argv[i] );  
   printf( "\n" );  
}  
  
int compare( const void *arg1, const void *arg2 )  
{  
   /* Compare all of both strings: */  
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );  
}  
```  
  
  **Junge verdient jede gute Bevorzugung**   
## .NET Framework-Entsprechung  
 [System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)  
  
## Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)