---
title: "bsearch_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "bsearch_s"
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
  - "bsearch_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "arrays [CRT], binäre Suche"
  - "bsearch_s-Funktion"
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# bsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt eine binäre Suche eines sortierten Arrays aus. Dies ist eine Version von [bsearch](../../c-runtime-library/reference/bsearch.md) mit Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
void *bsearch_s(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),  
   void * context  
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
 Rückruffunktion, die zwei Elemente vergleicht. Das erste Argument ist der `context`\-Zeiger. Das zweite Argument ist ein Zeiger auf den `key` für die Suche. Das dritte Argument ist ein Zeiger auf das Arrayelement, das mit `key` verglichen werden soll.  
  
 `context`  
 Ein Zeiger auf ein Objekt, auf das in der Vergleichsfunktion zugegriffen werden kann.  
  
## Rückgabewert  
 `bsearch_s` gibt einen Zeiger auf ein Vorkommen von`key` in dem Array zurück, auf das `base` verweist. Wenn `key` nicht gefunden wird, gibt die Funktion `NULL` zurück. Wenn das Array nicht in aufsteigender Reihenfolge sortiert ist oder doppelte Datensätze mit identischen Schlüsseln enthält, ist das Ergebnis nicht vorhersehbar.  
  
 Wenn ungültige Parameter an die Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno`auf `EINVAL` festgelegt, und die Funktion gibt `NULL` zurück. Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Fehlerbedingungen  
  
|||||||  
|-|-|-|-|-|-|  
|`key`|`base`|`compare`|`num`|`width`|`errno`|  
|`NULL`|alle|any|any|any|`EINVAL`|  
|any|`NULL`|alle|\!\= 0|alle|`EINVAL`|  
|any|any|any|any|\= 0|`EINVAL`|  
|alle|alle|`NULL`|ein|alle|`EINVAL`|  
  
## Hinweise  
 Die `bsearch_s`\-Funktion führt eine binäre Suche eines sortierten Arrays aus `num` Elementen aus, von denen jedes `width` Bytes groß ist. Der `base`\-Wert ist ein Zeiger auf die Basis des zu durchsuchenden Arrays, und `key` ist der gesuchte Wert. Der `compare`\-Parameter ist ein Zeiger auf eine vom Benutzer bereitgestellte Routine, die den angeforderten Schlüssel mit einem Arrayelement vergleicht und einen der folgenden Werte zur Angabe ihrer Beziehung zurückgibt:  
  
|Von der `compare`\-Routine zurückgegebener Wert|Beschreibung|  
|-----------------------------------------------------|------------------|  
|\< 0|Der Schlüssel ist kleiner als das Arrayelement.|  
|0|Schlüssel und Arrayelement sind gleich.|  
|\> 0|Der Schlüssel ist größer als das Arrayelement.|  
  
 Der `context`\-Zeiger kann nützlich sein, wenn die durchsuchte Datenstruktur Teil eines Objekts ist und die Vergleichsfunktion auf Member des Objekts zugreifen muss. Mithilfe der `compare`\-Funktion kann möglicherweise der void\-Zeiger in den passenden Objekttyp umgewandelt und auf Member des Objekts zugegriffen werden. Die Hinzufügung des `context`\-Parameters macht `bsearch_s` sicherer, da weiterer Kontext verwendet werden kann, um Fehler beim erneuten Eintreten zu vermeiden, die mit der Verwendung statischer Variablen zur Bereitstellung von Daten für die `compare`\-Funktion einhergehen können.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`bsearch_s`|\<stdlib.h\> und \<search.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Programm sortiert ein Zeichenfolgenarray mit [qsort\_s](../../c-runtime-library/reference/qsort-s.md) und verwendet anschließend bsearch\_s, um nach dem Wort „Katze“ zu suchen.  
  
```  
// crt_bsearch_s.cpp  
// This program uses bsearch_s to search a string array,  
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
#define ENGLISH_LOCALE "English_US.850"  
#endif  
  
#ifdef CODEPAGE_1252  
#define ENGLISH_LOCALE "English_US.1252"  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, char **str1, char **str2)  
{  
    char *s1 = *str1;  
    char *s2 = *str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
  
   char *key = "cat";  
   char **result;  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort_s( arr,  
            sizeof(arr)/sizeof(arr[0]),  
            sizeof( char * ),  
            (int (*)(void*, const void*, const void*))compare,  
            &locale(ENGLISH_LOCALE) );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch_s( &key,  
                                arr,  
                                sizeof(arr)/sizeof(arr[0]),  
                                sizeof( char * ),  
                                (int (*)(void*, const void*, const void*))compare,  
                                &locale(ENGLISH_LOCALE) );  
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
 <xref:System.Collections.ArrayList.BinarySearch*>  
  
## Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)