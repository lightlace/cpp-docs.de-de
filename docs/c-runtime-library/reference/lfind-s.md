---
title: "_lfind_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lfind_s"
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
  - "lfind_s"
  - "_lfind_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lfind_s-Funktion"
  - "Arrays [CRT], Suchen"
  - "Schlüssel, Suchen in Arrays"
  - "lfind_s-Funktion"
  - "Lineares Suchen"
  - "Suchen, Linear"
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _lfind_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt eine lineare Suche für den angegebenen Schlüssel aus.  Eine Version von [\_lfind](../../c-runtime-library/reference/lfind.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
void *_lfind_s(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### Parameter  
 `key`  
 Planen Sie für Suche für ein.  
  
 `base`  
 Zeiger zur Basis von Suchendaten.  
  
 `num`  
 Zahl Arrayelemente.  
  
 `size`  
 Größe von Arrayelementen in Bytes.  
  
 `compare`  
 Zeiger auf die Vergleichsroutine.  Der erste Parameter ist der `context` Zeiger.  Der zweite Parameter ist ein für Such\- zu verschlüsseln, Zeiger.  Der dritte Parameter ist ein Zeiger mit Schlüssel verglichen werden Arrayelement.  
  
 `context`  
 Ein Zeiger auf ein Objekt, auf das möglicherweise in der Vergleichsfunktion zugegriffen wird.  
  
## Rückgabewert  
 Wenn die Schlüssel gefunden wird, gibt `_lfind_s` einen Zeiger auf das Element des Arrays bei diesem `base` Entspricht `key` zurück.  Wenn der Schlüssel nicht gefunden wird, gibt `_lfind_s``NULL` zurück.  
  
 Wenn ungültige Parameter an die Funktion übergeben werden, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  
  
### Fehlerbedingungen  
  
|Schlüssel|base|compare|num|size|errno|  
|---------------|----------|-------------|---------|----------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|0 \(Null\)|`EINVAL`|  
|any|any|`NULL`|an|any|`EINVAL`|  
  
## Hinweise  
 Die `_lfind_s`\-Funktion führt eine lineare Suche für den Wert `key` in einem `num` \- Array Elemente, jedes von `width` Bytes aus.  Anders als `bsearch_s` erfordert `_lfind_s` das Array nicht sortiert werden.  Das `base`\-Argument ist ein Zeiger zur Basis des zu durchsuchenden Arrays.  Das `compare`\-Argument ist ein Zeiger auf eine vom Benutzer bereitgestellten Routine, die zwei Arrayelemente und vergleicht dann einen Wert zurückgibt, der die Beziehung angibt.  `_lfind_s` ruft die Routine `compare` mindestens einmal während der Suche auf und übergibt den `context` Zeiger und die Zeiger auf zwei Arrayelementen auf jedem Aufruf.  Die Routine `compare` muss die Elemente anschließend den Rückholwert ungleich 0 \(null\) \(Bedeutung, dass die Elemente unterscheiden\) oder das 0 \(vergleichen die Elemente signifikant, befinden\) identisch.  
  
 `_lfind_s` entspricht `_lfind` außer der Addition des `context` Zeigers für Argumente der Vergleichsfunktion und der Parameterliste der Funktion ähnelt.  Der `context` Zeiger kann nützlich sein, wenn die gesuchte Datenstruktur Teil eines Objekts ist und die `compare`\-Funktion Member des Objekts zugreifen muss.  Die `compare`\-Funktion kann den void\-Zeiger in die entsprechenden Objekttypen aufgelistet umwandeln und Member dieses Objekts zugreifen.  Die Einführung des Parameters `context` macht `_lfind_s` sicherer, da zusätzliche Kontext verwendet werden kann, um die Reentranzfehler zu vermeiden, die mithilfe von statischen Variablen, um Daten zur Verfügung stehen die `compare`\-Funktion zugeordnet sind.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_lfind_s`|\<search.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_lfind_s.cpp  
// This program uses _lfind_s to search a string array,  
// passing a locale as the context.  
// compile with: /EHsc  
#include <stdlib.h>  
#include <stdio.h>  
#include <search.h>  
#include <process.h>  
#include <locale.h>  
#include <locale>  
#include <windows.h>  
using namespace std;  
  
// The sort order is dependent on the code page.  Use 'chcp' at the  
// command line to change the codepage.  When executing this application,  
// the command prompt codepage must match the codepage used here:  
  
#define CODEPAGE_850  
  
#ifdef CODEPAGE_850  
// Codepage 850 is the OEM codepage used by the command line,  
// so \x00e1 is the German Sharp S  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char *s1 = *(char**)str1;  
    char *s2 = *(char**)str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
void find_it( char *key, char *array[], unsigned int num, locale &loc )  
{  
   char **result = (char **)_lfind_s( &key, array,   
                      &num, sizeof(char *), compare, &loc );  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "%s not found\n", key );  
}  
  
int main( )  
{  
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );  
}  
```  
  
  **weit gefunden**   
## .NET Framework-Entsprechung  
 <xref:System.Collections.ArrayList.Contains*>  
  
## Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort\_s](../../c-runtime-library/reference/qsort-s.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)