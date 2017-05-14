---
title: div | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- div
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
- div
dev_langs:
- C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 15
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
ms.openlocfilehash: e1e92656713a31d3057dfe180bd1cb4e819ceb5b
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="div"></a>div
Berechnet den Quotienten und den Rest von zwei ganzzahligen Werten.  
  
## <a name="syntax"></a>Syntax  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### <a name="parameters"></a>Parameter  
 `numer`  
 Der Zähler.  
  
 `denom`  
 Der Nenner.  
  
## <a name="return-value"></a>Rückgabewert  
 `div`, welches mithilfe von Argumenten des Typs `int` aufgerufen wurde, gibt eine Struktur des Typs `div_t` zurück, die den Quotienten und den Rest enthält. Der Rückgabewert der Überladung mit Argumenten vom Typ `long` ist `ldiv_t`. Sowohl `div_t` als auch `ldiv_t` werden in STDLIB.H. definiert.  
  
## <a name="remarks"></a>Hinweise  
 Die `div`-Funktion teilt `numer` durch `denom` und berechnet dadurch den Quotienten und den Rest. Die [div_t](../../c-runtime-library/standard-types.md)-Struktur enthält den Quotienten `int quot` und den Rest `int rem`. Das Zeichen des Quotienten entspricht dem Zeichen des mathematischen Quotienten. Der absolute Wert ist die größte ganze Zahl, die kleiner ist als der absolute Wert des mathematischen Quotienten. Wenn der Nenner 0 ist, wird das Programm mit einer Fehlermeldung beendet.  
  
 Die Überladungen, die Argumente des Typs `long` oder `long long` verwenden, sind nur für C++-Code verfügbar. Der Rückgabetyp [ldiv_t](../../c-runtime-library/standard-types.md) enthält die Member `long quot` und `long rem`, und der Rückgabetyp [lldiv_t](../../c-runtime-library/standard-types.md) enthält die Member `long long quot` und `long long rem`, die die gleiche Bedeutung wie die Member von `div_t` haben.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`div`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
```Output  
x is 876, y is 13  
The quotient is 67, and the remainder is 5  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)
