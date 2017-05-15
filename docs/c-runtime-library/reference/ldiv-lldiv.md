---
title: ldiv, lldiv | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ldiv
- lldiv
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
- ldiv
- lldiv
dev_langs:
- C++
helpviewer_keywords:
- ldiv function
- lldiv function
- quotients, computing
- computing remainders
- remainder computing
- computing quotients
ms.assetid: 68ab5d83-27a4-479c-9d52-d055eb139eca
caps.latest.revision: 12
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
ms.openlocfilehash: 3e7d21b1b5c6197c43ddc5730953f1a4a6259fc2
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="ldiv-lldiv"></a>ldiv, lldiv
Berechnet den Quotienten und den Rest von zwei ganzen Zahlen als eine Operation.  
  
## <a name="syntax"></a>Syntax  
  
```  
ldiv_t ldiv(  
   long numer,  
   long denom   
);  
lldiv_t lldiv(  
   long long numer,  
   long long denom   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `numer`  
 Zähler.  
  
 `denom`  
 Nenner.  
  
## <a name="return-value"></a>Rückgabewert  
 `ldiv` gibt eine Struktur des Typs [ldiv_t](../../c-runtime-library/standard-types.md) zurück, die sowohl den Quotienten als auch den Rest enthält. `lldiv` gibt eine Struktur des Typs [lldiv_t](../../c-runtime-library/standard-types.md) zurück, die sowohl den Quotienten als auch den Rest enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `ldiv` und `lldiv` teilen `numer` durch `denom` und berechnen dadurch den Quotienten und den Rest. Das Zeichen des Quotienten entspricht dem Zeichen des mathematischen Quotienten. Der absolute Wert des Quotienten ist die größte ganze Zahl, die kleiner ist als der absolute Wert des mathematischen Quotienten. Wenn der Nenner 0 ist, wird das Programm mit einer Fehlermeldung beendet. `ldiv` und `lldiv` sind nahezu identisch `div`, außer dass die Argumente von `ldiv` und die Mitglieder der zurückgegebene Struktur alle vom `long`-Typ sind, die Argumente von `lldiv` und die Mitglieder der zurückgegebenen Struktur jedoch vom `long long`-Typ sind.  
  
 Die Strukturen `ldiv_t` und `lldiv_t` werden in \<stdlib.h> definiert.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`ldiv`, `lldiv`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_ldiv.c  
  
#include <stdlib.h>  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   long x = 5149627, y = 234879;  
   ldiv_t div_result;  
  
   div_result = ldiv( x, y );  
   printf( "For %ld / %ld, the quotient is ", x, y );  
   printf( "%ld, and the remainder is %ld\n",   
            div_result.quot, div_result.rem );  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
For 5149627 / 234879, the quotient is 21, and the remainder is 217168  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)
