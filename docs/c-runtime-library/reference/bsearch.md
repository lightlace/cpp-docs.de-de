---
title: "bsearch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "bsearch"
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
  - "bsearch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "arrays [CRT], binäre Suche"
  - "bsearch-Funktion"
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# bsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt eine binäre Suche eines sortierten Arrays aus. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md).  
  
## Syntax  
  
```  
void *bsearch(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) (const void *key, const void *datum)   
);  
```  
  
#### Parameter  
 `key`  
 Das Objekt, nach dem gesucht werden soll.  
  
 `base`  
 Zeiger auf die Basis der Suchdaten.  
  
 `num`  
 Anzahl der Elemente.  
  
 `width`  
 Breite der Elemente.  
  
 `compare`  
 Rückruffunktion, die zwei Elemente vergleicht. Da erste ist ein Zeiger auf den Schlüssel für die Suche, und das zweite ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.  
  
## Rückgabewert  
 `bsearch` gibt einen Zeiger auf ein Vorkommen von `key` in dem Array zurück, auf das `base` verweist. Wenn `key` nicht gefunden wird, wird `NULL` zurückgegeben. Wenn das Array nicht in aufsteigender Reihenfolge sortiert ist oder doppelte Datensätze mit identischen Schlüsseln enthält, ist das Ergebnis nicht vorhersehbar.  
  
## Hinweise  
 Die `bsearch`\-Funktion führt eine binäre Suche eines sortierten Arrays aus `num` Elementen aus, von denen jedes `width` Bytes groß ist. Der `base`\-Wert ist ein Zeiger auf die Basis des zu durchsuchenden Arrays, und `key` ist der gesuchte Wert. Der `compare`\-Parameter ist ein Zeiger auf eine vom Benutzer bereitgestellte Routine, die den angeforderten Schlüssel mit einem Arrayelement vergleicht und einen der folgenden Werte zur Angabe ihrer Beziehung zurückgibt:  
  
|Von der `compare`\-Routine zurückgegebener Wert|Beschreibung|  
|-----------------------------------------------------|------------------|  
|\< 0|Der Schlüssel ist kleiner als das Arrayelement.|  
|0|Schlüssel und Arrayelement sind gleich.|  
|\> 0|Der Schlüssel ist größer als das Arrayelement.|  
  
 Diese Funktion überprüft ihre Parameter. Wenn `compare`, `key` oder `num``NULL` ist oder wenn `base``NULL` und \*`num` ungleich null ist oder wenn `width` null ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`bsearch`|\<stdlib.h\> und \<search.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Programm sortiert ein Zeichenfolgenarray mit „qsort“ und verwendet anschließend bsearch, um nach dem Wort „Katze“ zu suchen.  
  
```  
// crt_bsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( char **arg1, char **arg2 )  
{  
   /* Compare all of both strings: */  
   return _strcmpi( *arg1, *arg2 );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
   char **result;  
   char *key = "cat";  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const   
   void*, const void*))compare );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),  
                              sizeof( char * ), (int (*)(const void*, const void*))compare );  
   if( result )  
      printf( "\n%s found at %Fp\n", *result, result );  
   else  
      printf( "\nCat not found!\n" );  
}  
```  
  
```Output  
Katze Kuh Hund Ziege Pferd Mensch Schwein Ratte Katze gefunden an 002F0F04  
```  
  
## .NET Framework-Entsprechung  
 [System::Collections::ArrayList::BinarySearch](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)  
  
## Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)