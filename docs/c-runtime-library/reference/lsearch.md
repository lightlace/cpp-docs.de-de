---
title: "lsearch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch"
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
  - "lsearch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lsearch-Funktion"
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _lsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt eine lineare Suche für einen Wert aus; fügt Ende der Liste hinzu, wenn Sie nicht gefunden werden.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md).  
  
## Syntax  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### Parameter  
 `key`  
 Planen Sie für Suche für ein.  
  
 `base`  
 Zeiger zur Basis des zu durchsuchenden Arrays.  
  
 `num`  
 Anzahl der Elemente.  
  
 `width`  
 Breite jedes Arrayelements.  
  
 `compare`  
 Zeiger auf die Vergleichsroutine.  Der erste Parameter ist ein Zeiger auf die Schlüssel für die Suche.  Der zweite Parameter ist ein Zeiger auf ein mit der Schlüssel verglichen werden Arrayelement.  
  
## Rückgabewert  
 Wenn die Schlüssel gefunden wird, gibt `_lsearch` einen Zeiger auf das Element des Arrays bei diesem `base` Entspricht `key` zurück.  Wenn der Schlüssel nicht gefunden wird, gibt `_lsearch` einen Zeiger auf das neu hinzugefügten Element am Ende des Arrays zurück.  
  
## Hinweise  
 Die `_lsearch`\-Funktion führt eine lineare Suche für den Wert `key` in einem `num` \- Array Elemente, jedes von `width` Bytes aus.  Anders als `bsearch` erfordert `_lsearch` das Array nicht sortiert werden.  Wenn `key` nicht gefunden wird, wird `_lsearch` dem Ende des Arrays hinzu und inkrementiert `num`.  
  
 Das `compare`\-Argument ist ein Zeiger auf eine vom Benutzer bereitgestellten Routine, die zwei Arrayelemente verglichen und einen Wert zurückgibt, der die Beziehung angibt.  `_lsearch` ruft die Routine `compare` mindestens einmal während der Suche auf und übergibt Zeiger zu zwei Arrayelementen auf jedem Aufruf.  `compare` muss über Elemente vergleichen und entweder dem Wert ungleich 0 \(null\) \(die Elemente sind signifikant Sie unterscheiden\) oder 0 zurückgeben \(die Elemente signifikant, befinden\) identisch.  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `compare`, `key` oder `num` ist `NULL` oder `base` und NULL ist \*`num` ist ungleich 0 \(null\), oder, wenn `width` kleiner als null ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_lsearch`|\<search.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_lsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main(void)  
{  
   char * wordlist[4] = { "hello", "thanks", "bye" };  
                            // leave room to grow...  
   int n = 3;  
   char **result;  
   char *key = "extra";  
   int i;  
  
   printf( "wordlist before _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
  
   result = (char **)_lsearch( &key, wordlist,   
                      &n, sizeof(char *), compare );  
  
   printf( "wordlist after _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
}  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
```  
  
  **Wörterliste vor \_lsearch: Dank abgelegen Hello**  
**Wörterliste nach \_lsearch: Hello Danktschüssextrakosten**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)