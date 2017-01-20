---
title: "qsort_s"
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
  - "qsort_s"
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
  - "qsort_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Arrays [C++], Sortieren"
  - "qsort_s-Funktion"
  - "Schnellsortierungsalgorithmus"
  - "Sortieren von Arrays"
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# qsort_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt eine schnelle Sortierung aus.  Eine Version von [qsort](../../c-runtime-library/reference/qsort.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
void qsort_s(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(void *, const void *, const void *),  
   void * context  
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
 Vergleichsfunktion.  Das erste Argument ist der `context` Zeiger.  Das zweite Argument ist ein Zeiger auf `key` für die Suche.  Das dritte Argument ist ein Zeiger mit `key` verglichen werden Arrayelement.  
  
 `context`  
 Ein Zeiger auf einen Kontext, der auf jedes Objekt sein kann, das die `compare` \- Routine zugreifen muss.  
  
## Hinweise  
 Die `qsort_s`\-Funktion implementiert einen QuickSortierungsalgorithmus, um ein Array, `num`\-Elemente jedes von `width` Bytes zu sortieren.  Das Argument `base` ist ein Zeiger zur Basis des zu sortierende Arrays.  `qsort_s` überschreibt dieses Array mit den sortierten Elemente.  Das Argument `compare` ist ein Zeiger auf eine vom Benutzer bereitgestellten Routine, die zwei Arrayelemente verglichen und einen Wert zurückgibt, der die Beziehung angibt.  `qsort_s` ruft die Routine `compare` mindestens einmal bei der Sortierung auf und übergibt Zeiger zu zwei Arrayelementen auf jedes Aufrufs:  
  
```  
compare( context, (void *) & elem1, (void *) & elem2 );  
```  
  
 Die Routine muss die Elemente vergleichen und dann einen der folgenden Werte zurückgeben:  
  
|Rückgabewert|**Beschreibung**|  
|------------------|----------------------|  
|\< 0|`elem1` kleiner als `elem2`|  
|0|`elem1` entspricht `elem2`|  
|\> 0|`elem1` größer als `elem2`|  
  
 Das Array ist in aufsteigender Reihenfolge sortiert, wie von der Vergleichsfunktion definiert.  Um ein Array in absteigender Reihenfolge zu sortieren, kehren Sie dem Sinne "in größerem als" und "kleiner als" in der Vergleichsfunktion um.  
  
 Wenn ungültige Parameter an die Funktion übergeben werden, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, kehrt die Funktion zurück und `errno` ist auf `EINVAL` festgelegt.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Fehlerbedingungen  
  
|Schlüssel|base|compare|num|width|errno|  
|---------------|----------|-------------|---------|-----------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|\<\= 0|`EINVAL`|  
|any|any|`NULL`|any|any|`EINVAL`|  
  
 `qsort_s` verfügt, das gleiche Verhalten wie `qsort` hat aber den Parameter `context` und `errno` fest.  Durch einen `context`\-Parameter übergeben, können Vergleichsfunktionen einen Objektzeiger verwenden, um die Objektfunktionalität oder auf andere Informationen zugreifen, die durch einen Elementzeiger nicht zugänglich sind.  Die Einführung des Parameters `context` macht `qsort_s` sicherer, da `context` verwendet werden kann, um die Reentranzfehler zu vermeiden, die mithilfe von statischen Variablen, um freigegebene Informationen zur Funktion `compare` auszuführen eingegeben werden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`qsort_s`|\<stdlib.h und\> search.h \<\>|  
  
 Um zusätzliche Kompatibilitätsinformation finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** Alle Versionen der [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie der Parameter `context` in der Funktion `qsort_s` verwendet.  Der Parameter `context` vereinfacht, threadsichere Sortierungen auszuführen.  Anstatt, statische Variablen zu verwenden, die synchronisiert werden, müssen Threadsicherheit sicherzustellen, führen Sie einen anderen Parameter `context` in jeder Sortierung.  In diesem Beispiel wird ein `context` Gebietsschemaobjekt als Parameter verwendet.  
  
```  
// crt_qsort_s.cpp  
// compile with: /EHsc /MT  
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
// so \x00e1 is the German Sharp S in that codepage and \x00a4  
// is the n tilde.  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
#define SPANISH_LOCALE "Spanish_Spain.850"  
#define ENGLISH_LOCALE "English_US.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S and \x001f for the n tilde.  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
#define SPANISH_LOCALE "Spanish_Spain.1252"  
#define ENGLISH_LOCALE "English_US.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making sort_array vulnerable to thread  
// conflicts.  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char s1[256];  
    char s2[256];  
    strcpy_s(s1, 256, *(char**)str1);  
    strcpy_s(s2, 256, *(char**)str2);  
    _strlwr_s( s1, sizeof(s1) );  
    _strlwr_s( s2, sizeof(s2) );  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(s1,   
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);  
  
}  
  
void sort_array(char *array[], int num, locale &loc)  
{  
    qsort_s(array, num, sizeof(char*), compare, &loc);  
}  
  
void print_array(char *a[], int c)  
{  
   for (int i = 0; i < c; i++)  
     printf("%s ", a[i]);  
   printf("\n");  
  
}  
  
void sort_german(void * Dummy)  
{  
   sort_array(array1, 6, locale(GERMAN_LOCALE));  
}  
  
void sort_spanish(void * Dummy)  
{     
   sort_array(array2, 3, locale(SPANISH_LOCALE));       
}  
  
void sort_english(void * Dummy)  
{     
   sort_array(array3, 3, locale(ENGLISH_LOCALE));     
}  
  
int main( )  
{  
  
   int i;  
   HANDLE threads[3];  
  
   printf("Unsorted input:\n");  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
   // Create several threads that perform sorts in different  
   // languages at the same time.   
  
   threads[0] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_german , 0, NULL));  
   threads[1] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_spanish, 0, NULL));  
   threads[2] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_english, 0, NULL));  
  
   for (i = 0; i < 3; i++)  
   {  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
      {  
         printf("Error creating threads.\n");  
         exit(1);  
      }  
   }  
  
   // Wait until all threads have terminated.  
   WaitForMultipleObjects(3, threads, true, INFINITE);  
  
   printf("Sorted output: \n");  
  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
}  
```  
  
## Beispielausgabe  
  
```  
Unsorted input:  
weiß weis annehmen weizen Zeit weit   
Español España espantado   
table tableux tablet   
Sorted output:   
annehmen weiß weis weit weizen Zeit   
España Español espantado   
table tablet tableux  
```  
  
## .NET Framework-Entsprechung  
 <xref:System.Collections.ArrayList.Sort*>  
  
## Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)