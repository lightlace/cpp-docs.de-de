---
title: _lsearch | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lsearch
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
- _lsearch
- lsearch
dev_langs:
- C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 86dd9925775d50a8e1c79f677f3e5b1d9ad3ae37
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="lsearch"></a>_lsearch
Führt eine lineare Suche nach einem Wert aus. Fügt ihn am Ende der Liste hinzu, falls nicht gefunden. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `key`  
 Das Objekt, nach dem gesucht werden soll.  
  
 `base`  
 Zeiger auf der Basis des zu durchsuchenden Arrays.  
  
 `num`  
 Anzahl der Elemente.  
  
 `width`  
 Die Breite jedes Array-Elements.  
  
 `compare`  
 Ein Zeiger auf die Vergleichsroutine. Der erste Parameter ist ein Zeiger auf den Schlüssel für die Suche. Der zweite Parameter ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn der Schlüssel gefunden wird, gibt `_lsearch` einen Zeiger auf das Element des Arrays bei `base` zurück, das `key` entspricht. Wenn der Schlüssel nicht gefunden wird, gibt `_lsearch` einen Zeiger auf das neu hinzugefügte Element am Ende des Arrays zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_lsearch`-Funktion führt eine lineare Suche nach dem Wert `key` in einem Array aus `num`-Elementen durch, die jeweils aus `width`-Bytes bestehen. Im Gegensatz zu `bsearch`, muss bei `_lsearch` kein Array sortiert werden. Wenn `key` nicht gefunden wird, fügt `_lsearch` es am Ende des Arrays hinzu und inkrementiert `num`.  
  
 Das `compare`-Argument ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und einen Wert zurückgibt, der die Beziehung angibt. `_lsearch` ruft die `compare`-Routine einmal oder mehrere Male während der Suche auf, wodurch bei jedem Aufruf Zeiger auf zwei Array-Elemente übergeben werden. `compare` muss die Elemente vergleichen und entweder ungleich null (d.h. die Elemente unterscheiden sich) oder 0 (d.h. die Elemente sind identisch) zurückgeben.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `compare`, dann ist `key` oder `num` `NULL` oder wenn `base` NULL ist und *`num` ungleich 0 oder `width` kleiner als 0 ist, wird der Handler für ungültige Parameter aufgerufen, siehe Beschreibung unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL`zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_lsearch`|\<search.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
wordlist before _lsearch: hello thanks bye  
wordlist after _lsearch: hello thanks bye extra  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)
