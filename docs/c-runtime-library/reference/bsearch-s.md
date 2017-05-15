---
title: bsearch_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- bsearch_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- bsearch_s
dev_langs:
- C++
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch_s function
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 67caa4f6f6f9ba43c5d4b8a23af8be9bebcc717b
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="bsearchs"></a>bsearch_s
Führt eine binäre Suche eines sortierten Arrays aus. Dies ist eine Version von [bsearch](../../c-runtime-library/reference/bsearch.md) mit Sicherheitsverbesserungen, wie dies unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `key`  
 Das Objekt, nach dem gesucht werden soll.  
  
 `base`  
 Zeiger auf die Basis der Suchdaten.  
  
 `num`  
 Anzahl der Elemente.  
  
 `width`  
 Breite der Elemente.  
  
 `compare`  
 Rückruffunktion, die zwei Elemente vergleicht. Das erste Argument ist der `context` -Zeiger. Das zweite Argument ist ein Zeiger auf den `key` für die Suche. Das dritte Argument ist ein Zeiger auf das Arrayelement, das mit `key`verglichen werden soll.  
  
 `context`  
 Ein Zeiger auf ein Objekt, auf das in der Vergleichsfunktion zugegriffen werden kann.  
  
## <a name="return-value"></a>Rückgabewert  
 `bsearch_s` gibt einen Zeiger auf ein Vorkommen von `key` in dem Array zurück, auf das `base` verweist. Wenn `key` nicht gefunden wird, gibt die Funktion `NULL`zurück. Wenn das Array nicht in aufsteigender Reihenfolge sortiert ist oder doppelte Datensätze mit identischen Schlüsseln enthält, ist das Ergebnis nicht vorhersehbar.  
  
 Wenn ungültige Parameter an die Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parameter Validation](../../c-runtime-library/parameter-validation.md)beschrieben. If execution is allowed to continue, `errno` is set to `EINVAL` and the function returns `NULL`. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|||||||  
|-|-|-|-|-|-|  
|`key`|`base`|`compare`|`num`|`width`|`errno`|  
|`NULL`|alle|alle|alle|alle|`EINVAL`|  
|alle|`NULL`|alle|!= 0|alle|`EINVAL`|  
|alle|alle|alle|alle|= 0|`EINVAL`|  
|alle|alle|`NULL`|ein|alle|`EINVAL`|  
  
## <a name="remarks"></a>Hinweise  
 Die `bsearch_s` -Funktion führt eine binäre Suche eines sortierten Arrays aus `num` Elementen aus, von denen jedes `width` Bytes groß ist. Der `base` -Wert ist ein Zeiger auf die Basis des zu durchsuchenden Arrays, und `key` ist der gesuchte Wert. Der `compare` -Parameter ist ein Zeiger auf eine vom Benutzer bereitgestellte Routine, die den angeforderten Schlüssel mit einem Arrayelement vergleicht und einen der folgenden Werte zur Angabe ihrer Beziehung zurückgibt:  
  
|Von der `compare` -Routine zurückgegebener Wert|Beschreibung|  
|-----------------------------------------|-----------------|  
|\< 0|Der Schlüssel ist kleiner als das Arrayelement.|  
|0|Schlüssel und Arrayelement sind gleich.|  
|> 0|Der Schlüssel ist größer als das Arrayelement.|  
  
 Der `context` -Zeiger kann nützlich sein, wenn die durchsuchte Datenstruktur Teil eines Objekts ist und die Vergleichsfunktion auf Member des Objekts zugreifen muss. Mithilfe der `compare` -Funktion kann möglicherweise der void-Zeiger in den passenden Objekttyp umgewandelt und auf Member des Objekts zugegriffen werden. Die Hinzufügung des `context` -Parameters macht `bsearch_s` sicherer, da weiterer Kontext verwendet werden kann, um Fehler beim erneuten Eintreten zu vermeiden, die mit der Verwendung statischer Variablen zur Bereitstellung von Daten für die `compare` -Funktion einhergehen können.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`bsearch_s`|\<stdlib.h> und \<search.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Dieses Programm sortiert ein Zeichenfolgenarray mit [qsort_s](../../c-runtime-library/reference/qsort-s.md)und verwendet anschließend bsearch_s, um nach dem Wort „Katze“ zu suchen.  
  
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
cat cow dog goat horse human pig rat  
cat found at 002F0F04  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)
