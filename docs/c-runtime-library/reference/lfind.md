---
title: "_lfind"
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
  - "_lfind"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lfind"
  - "_lfind"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lfind-Funktion"
  - "Arrays [CRT], Suchen"
  - "Suchen von Schlüsseln in Arrays"
  - "lfind-Funktion"
  - "Lineares Suchen"
  - "Suchen, Linear"
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: 20
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# _lfind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt eine lineare Suche für den angegebenen Schlüssel aus.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md).  
  
## Syntax  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### Parameter  
 `key`  
 Planen Sie für Suche für ein.  
  
 `base`  
 Zeiger zur Basis von Suchendaten.  
  
 `num`  
 Zahl Arrayelemente.  
  
 `width`  
 Breite von Arrayelementen.  
  
 `compare`  
 Zeiger auf die Vergleichsroutine.  Der erste Parameter ist ein für Such\- zu verschlüsseln, Zeiger.  Der zweite Parameter ist ein Zeiger mit Schlüssel verglichen werden Arrayelement.  
  
## Rückgabewert  
 Wenn die Schlüssel gefunden wird, gibt `_lfind` einen Zeiger auf das Element des Arrays bei diesem `base` Entspricht `key` zurück.  Wenn der Schlüssel nicht gefunden wird, gibt `_lfind``NULL` zurück.  
  
## Hinweise  
 Die `_lfind`\-Funktion führt eine lineare Suche für den Wert `key` in einem `num` \- Array Elemente, jedes von `width` Bytes aus.  Anders als `bsearch` erfordert `_lfind` das Array nicht sortiert werden.  Das `base`\-Argument ist ein Zeiger zur Basis des zu durchsuchenden Arrays.  Das `compare`\-Argument ist ein Zeiger auf eine vom Benutzer bereitgestellten Routine, die zwei Arrayelemente und vergleicht dann einen Wert zurückgibt, der die Beziehung angibt.  `_lfind` ruft die Routine `compare` mindestens einmal während der Suche auf und übergibt Zeiger zu zwei Arrayelementen auf jedem Aufruf.  Die Routine `compare` muss die Elemente und dann den Rückholwert ungleich 0 \(null\) \(die Elemente sind signifikant Sie unterscheiden\) oder das 0 \(vergleichen die Elemente signifikant, befinden\) identisch.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `compare`, `key` oder `num` ist `NULL` oder `base` und NULL ist \*`num` ist ungleich 0 \(null\), oder, wenn `width` kleiner als null ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_lfind`|\<search.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_lfind.c  
// This program uses _lfind to search a string array  
// for an occurrence of "hello".  
  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
  
int main( )  
{  
   char *arr[] = {"Hi", "Hello", "Bye"};  
   int n = sizeof(arr) / sizeof(char*);  
   char **result;  
   char *key = "hello";  
  
   result = (char **)_lfind( &key, arr,   
                      &n, sizeof(char *), compare );  
  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "hello not found!\n" );  
}  
```  
  
  **Hello gefunden**   
## .NET Framework-Entsprechung  
 [System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)  
  
## Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)