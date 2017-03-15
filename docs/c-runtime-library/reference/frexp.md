---
title: frexp | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- frexp
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- frexp
- _frexpl
dev_langs:
- C++
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1f255fbc6eb63374a8651a11abaf0266ed9cfd6f
ms.lasthandoff: 02/24/2017

---
# <a name="frexp"></a>frexp
Ruft die Mantisse und den Exponenten einer Gleitkommazahl ab  
  
## <a name="syntax"></a>Syntax  
  
```  
double frexp(  
   double x,  
   int *expptr   
);  
float frexp(  
   float x,  
   int * expptr  
);  // C++ only  
long double frexp(  
   long double x,  
   int * expptr  
);  // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Gleitkommawert.  
  
 `expptr`  
 Zeiger auf gespeicherten Integer-Exponenten  
  
## <a name="return-value"></a>Rückgabewert  
 `frexp` gibt die Mantisse zurück. Wenn `x` 0 ist, gibt die Funktion 0 für die Mantisse und den Exponenten zurück. Wenn `expptr` `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, setzt diese Funktion `errno` auf `EINVAL` und gibt "0" zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `frexp` gliedert den Gleitkommawert (`x`) in einer Mantisse (`m`) und einem Exponenten (`n`), sodass der absolute Wert `m` größer gleich 0,5 und kleiner als 1,0 und `x` = `m`*2<sup>n</sup> ist. Der Integer-Exponent `n` wird an dem Speicherort gespeichert, auf den `expptr` zeigt.  
  
 Da C++ ein Überladen zulässt, können Sie Überladungen von `frexp` aufrufen. In einem C-Programm verwendet `frexp` immer einen double- und einen Integer-Wert und gibt einen double zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`frexp`|\<math.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_frexp.c  
// This program calculates frexp( 16.4, &n )  
// then displays y and n.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y;  
   int n;  
  
   x = 16.4;  
   y = frexp( x, &n );  
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );  
}  
```  
  
```Output  
frexp( 16.400000, &n ) = 0.512500, n = 5  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)
