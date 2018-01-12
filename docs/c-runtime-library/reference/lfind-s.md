---
title: _lfind_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lfind_s
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
- lfind_s
- _lfind_s
dev_langs: C++
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bff33c66ebe8bdb2b5eb497aad2e3a11bc04a76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="lfinds"></a>_lfind_s
Führt eine lineare Suche für den angegebenen Schlüssel aus. Dies ist eine Version von [_lfind](../../c-runtime-library/reference/lfind.md) mit Sicherheitserweiterungen, wie in den [Sicherheitsfunktionen in CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `key`  
 Das Objekt, nach dem gesucht werden soll.  
  
 `base`  
 Zeiger auf die Basis der Suchdaten.  
  
 `num`  
 Die Anzahl der Arrayelemente.  
  
 `size`  
 Die Größe der Arrayelemente in Bytes.  
  
 `compare`  
 Zeiger auf die Vergleichsroutine. Der erste Parameter ist der `context`-Zeiger. Der zweite Parameter ist ein Zeiger auf den Schlüssel für die Suche. Der dritte Parameter ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.  
  
 `context`  
 Ein Zeiger auf ein Objekt, auf das in der Vergleichsfunktion zugegriffen werden kann.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn der Schlüssel gefunden wird, gibt `_lfind_s` einen Zeiger auf das Arrayelement bei `base` zurück, das `key` entspricht. Wenn der Schlüssel nicht gefunden wird, gibt `_lfind_s` `NULL` zurück.  
  
 Wenn ungültige Parameter an die Funktion übergeben werden, ruft sie den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parametervalidierung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL`zurück.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|Key|Basis|compare|num|size|errno|  
|---------|----------|-------------|---------|----------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|!= 0|any|`EINVAL`|  
|any|any|any|any|Null|`EINVAL`|  
|any|any|`NULL`|ein|alle|`EINVAL`|  
  
## <a name="remarks"></a>Hinweise  
 Die `_lfind_s`-Funktion führt eine lineare Suche nach dem Wert `key` in einem Array aus `num`-Elementen durch, die jeweils aus `width`-Bytes bestehen. Im Gegensatz zu `bsearch_s` muss bei `_lfind_s` kein Array sortiert werden. Das `base`-Argument ist ein Zeiger auf die Basis des zu suchenden Arrays. Das `compare`-Argument ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Arrayelemente vergleicht und einen Wert zurückgibt, der die Beziehung angibt. `_lfind_s` ruft die `compare`-Routine einmal oder mehrere Male während der Suche auf, wodurch bei jedem Aufruf der `context`-Zeiger übergeben wird und auf zwei Arrayelemente zeigt. Die `compare`-Routine muss die Elemente vergleichen und entweder ungleich null (d.h. die Elemente unterscheiden sich) oder 0 (d.h. die Elemente sind identisch) zurückgeben.  
  
 `_lfind_s` ähnelt `_lfind` mit Ausnahme der Hinzufügung des `context`-Zeigers auf den Argumenten der Vergleichsfunktion und der Parameterliste der Funktion. Der `context`-Zeiger kann nützlich sein, wenn die durchsuchte Datenstruktur Teil eines Objekts ist und die `compare`-Funktion auf Member des Objekts zugreifen muss. Mithilfe der `compare`-Funktion kann möglicherweise der void-Zeiger in den passenden Objekttyp umgewandelt und auf Member des Objekts zugegriffen werden. Die Hinzufügung des `context`-Parameters macht `_lfind_s` sicherer, da weiterer Kontext verwendet werden kann, um Probleme beim Wiedereintreten zu vermeiden, die mit der Verwendung statischer Variablen zur Bereitstellung von Daten für die `compare`-Funktion einhergehen können.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_lfind_s`|\<search.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
weit found  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort_s](../../c-runtime-library/reference/qsort-s.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)