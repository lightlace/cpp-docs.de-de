---
title: _lfind | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lfind
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
- lfind
- _lfind
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: 20
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
ms.openlocfilehash: 7c597501d90e4816ffda3b0300109d3b51afc51c
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="lfind"></a>_lfind
Führt eine lineare Suche für den angegebenen Schlüssel aus. Es ist eine sicherere Version dieser Funktion verfügbar. Siehe [_lfind_s](../../c-runtime-library/reference/lfind-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `key`  
 Das Objekt, nach dem gesucht werden soll.  
  
 `base`  
 Zeiger auf die Basis der Suchdaten.  
  
 `num`  
 Die Anzahl der Arrayelemente.  
  
 `width`  
 Die Breite von Arrayelementen.  
  
 `compare`  
 Zeiger auf die Vergleichsroutine. Der erste Parameter ist ein Zeiger auf den Schlüssel für die Suche. Der zweite Parameter ist ein Zeiger auf das Arrayelement, das mit dem Schlüssel verglichen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn der Schlüssel gefunden wird, gibt `_lfind` einen Zeiger auf das Arrayelement bei `base` zurück, das `key` entspricht. Wenn der Schlüssel nicht gefunden wird, gibt `_lfind` an `NULL` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_lfind`-Funktion führt eine lineare Suche nach dem Wert `key` in einem Array aus `num`-Elementen durch, die jeweils aus `width`-Bytes bestehen. Im Gegensatz zu `bsearch` muss bei `_lfind` kein Array sortiert werden. Das `base`-Argument ist ein Zeiger auf die Basis des zu suchenden Arrays. Das `compare`-Argument ist ein Zeiger auf eine benutzerdefinierte Routine, die zwei Arrayelemente vergleicht und einen Wert zurückgibt, der die Beziehung angibt. `_lfind` ruft die `compare`-Routine einmal oder mehrere Male während der Suche auf, wodurch bei jedem Aufruf Zeiger auf zwei Arrayelemente übergeben werden. Die `compare`-Routine muss die Elemente vergleichen und anschließend ungleich null (d.h. die Elemente unterscheiden sich) oder 0 (d.h. die Elemente sind identisch) zurückgeben.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `compare`, dann ist `key` oder `num` `NULL` oder wenn `base` NULL ist und *`num` ungleich 0 oder `width` kleiner als 0 ist, wird der Handler für ungültige Parameter aufgerufen, siehe Beschreibung unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL`zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_lfind`|\<search.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Hello found  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)
