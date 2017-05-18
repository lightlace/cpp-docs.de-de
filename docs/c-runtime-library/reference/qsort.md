---
title: qsort | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- qsort
dev_langs:
- C++
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 19
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: b71bdc6b2b2bff50645a7ce8ae1ef88ad4d6dd91
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="qsort"></a>qsort
Führt eine schnelle Sortierung aus. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [qsort_s](../../c-runtime-library/reference/qsort-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `base`  
 Start des Zielarrays.  
  
 `num`  
 Arraygröße in Elementen.  
  
 `width`  
 Elementgröße in Bytes.  
  
 `compare`  
 Zeiger auf eine benutzerdefinierte Routine, die zwei Elemente des Arrays vergleicht und einen Wert zurückgibt, der ihre Beziehung angibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `qsort`-Funktion implementiert einen Schnellsortierungsalgorithmus, um ein Array von `num`-Elementen zu sortieren, die jeweils aus `width`-Bytes bestehen. Das `base`-Argument ist ein Zeiger auf die Basis des Arrays, das sortiert werden soll. `qsort` überschreibt dieses Array mit den sortierten Elementen.  
  
 `qsort` ruft die `compare`-Routine einmal oder mehrere Male während der Sortierung auf, wodurch bei jedem Aufruf Zeiger auf zwei Arrayelemente übergeben werden.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 Die Routine vergleicht die Elemente und gibt einen der folgenden Werte zurück.  
  
|Vergleich des Rückgabewerts der Funktion|Beschreibung|  
|-----------------------------------|-----------------|  
|< 0|`elem1` kleiner als `elem2`|  
|0|`elem1` gleich `elem2`|  
|> 0|`elem1` größer als `elem2`|  
  
 Das Array wird in aufsteigender Reihenfolge sortiert, wie von der Vergleichsfunktion definiert. Kehren Sie den Sinn der „größer als“ und „kleiner als“ in der Vergleichsfunktion um, um ein Array in absteigender Reihenfolge zu sortieren.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `compare` oder `num` `NULL`, oder wenn `base` `NULL` und *`num` ungleich NULL ist, oder wenn `width` weniger als NULL ist, wird der ungültige Parametertyphandler aufgerufen, so wie in der [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird die Funktion zurückgegeben und `errno` auf `EINVAL` festgesetzt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`qsort`|\<stdlib.h> und \<search.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_qsort.c  
// arguments: every good boy deserves favor  
  
/* This program reads the command-line  
 * parameters and uses qsort to sort them. It  
 * then displays the sorted arguments.  
 */  
  
#include <stdlib.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main( int argc, char **argv )  
{  
   int i;  
   /* Eliminate argv[0] from sort: */  
   argv++;  
   argc--;  
  
   /* Sort remaining args using Quicksort algorithm: */  
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );  
  
   /* Output sorted list: */  
   for( i = 0; i < argc; ++i )  
      printf( " %s", argv[i] );  
   printf( "\n" );  
}  
  
int compare( const void *arg1, const void *arg2 )  
{  
   /* Compare all of both strings: */  
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );  
}  
```  
  
```Output  
boy deserves every favor good  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)
