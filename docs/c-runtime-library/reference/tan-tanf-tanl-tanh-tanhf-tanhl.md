---
title: tan, tanf, tanl, tanh, tanhf, tanhl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tanhf
- tanh
- tan
- tanhl
- tanf
- tanl
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
- tanh
- tan
- _tanl
- tanl
- _tanhl
- tanf
- tanhf
- tanhl
dev_langs:
- C++
helpviewer_keywords:
- tanl function
- tanhl function
- _tanl function
- _tanhl function
- tan function
- calculating tangents
- tangent
- tanh function
- tanhf function
- tanf function
- trigonometric functions
- hyperbolic functions
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 94ad2866dc8b2284d674ccfa284646aac9a68efa
ms.lasthandoff: 02/24/2017

---
# <a name="tan-tanf-tanl-tanh-tanhf-tanhl"></a>tan, tanf, tanl, tanh, tanhf, tanhl
Berechnet den Tangens (`tan`, `tanf` oder `tanl`) oder den Hyperbeltangens (`tanh`, `tanhf` oder `tanhl`).  
  
## <a name="syntax"></a>Syntax  
  
```  
double tan(  
   double x   
);  
float tan(  
   float x   
);  // C++ only  
long double tan(  
   long double x  
);  // C++ only  
float tanf(  
   float x   
);  
long double tanl(  
   long double x  
);  
double tanh(  
   double x   
);  
float tanh(  
   float x   
);  // C++ only  
long double tanh(  
   long double x  
);  // C++ only  
float tanhf(  
   float x   
);  
long double tanhl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Winkel im Bogenmaß.  
  
## <a name="return-value"></a>Rückgabewert  
 Die `tan`-Funktionen geben den Tangens von `x` zurück. Wenn `x` größer oder gleich 263 oder kleiner oder gleich – 263 ist, kommt es im Ergebnis zu einem Bedeutungsverlust.  
  
 Die `tanh`-Funktionen geben den Hyperbeltangens von `x` zurück. Es gibt keine Fehlerrückgabe.  
  
|Eingabe|SEH-Ausnahme|`Matherr`-Ausnahme|  
|-----------|-------------------|-------------------------|  
|± QNAN,IND|Keine|_DOMAIN|  
|± ∞  (`tan`, `tanf`)|`INVALID`|_DOMAIN|  
  
## <a name="remarks"></a>Hinweise  
 Da C++ das Überladen zulässt, können Sie Überladungen von `tan` und `tanh` aufrufen, die `float`- oder `long double`-Werte verwenden und zurückgeben. In einem C-Programm verwenden `tan` und `tanh` immer `double` und geben "Double" auch zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`tan`, `tanf`, `tanl`, `tanh`, `tanhf`, `tanhl`|\<math.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_tan.c  
// This program displays the tangent of pi / 4  
// and the hyperbolic tangent of the result.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = tan( pi / 4 );  
   y = tanh( x );  
   printf( "tan( %f ) = %f\n", pi/4, x );  
   printf( "tanh( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
tan( 0.785398 ) = 1.000000  
tanh( 1.000000 ) = 0.761594  
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
  
-   [System::Math::Tan](https://msdn.microsoft.com/en-us/library/system.math.tan.aspx)  
  
-   [System::Math::Tanh](https://msdn.microsoft.com/en-us/library/system.math.tanh.aspx)  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkomma-Unterstützung](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [_CItan](../../c-runtime-library/citan.md)
