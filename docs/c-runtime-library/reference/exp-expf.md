---
title: EXP, Expf, Expl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- expf
- expl
- exp
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
- _expl
- expf
- expl
- exp
dev_langs: C++
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0702b99990728bdb732654fdd1eacbefa373dda6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exp-expf-expl"></a>EXP, Expf, expl
Berechnet den Bezeichner.  
  
## <a name="syntax"></a>Syntax  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
long double expl(  
   long double x  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `x`  
 Der Gleitkommadatentyp Wert exponentiate den natürlichen Logarithmus zur Basis *e* durch.  
  
## <a name="return-value"></a>Rückgabewert  
 Die `exp` Funktionen zurück, den exponentiellen Wert des Parameters Gleitkomma *x*, wenn erfolgreich. D. h. das Ergebnis ist *e*<sup>*x*</sup>, wobei *e* stellt die Basis des natürlichen Logarithmus. Auf die Funktion zurückgibt, INF (Unendlichkeit) einen Überlauf und Unterlauf `exp` gibt 0 zurück.  
  
|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|  
|-----------|-------------------|-----------------------|  
|± Stilles NaN, unbestimmt|Keiner|_DOMAIN|  
|± Unendlich|INVALID|_DOMAIN|  
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|  
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|  
  
 Die `exp` Funktion verfügt über eine Implementierung, die Streaming SIMD Extensions 2 (SSE2) verwendet. Informationen und Einschränkungen zur Verwendung der SSE2-Implementierung finden Sie unter [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
## <a name="remarks"></a>Hinweise  
 C++ das Überladen zulässt, sodass Sie Überladungen von aufrufen können `exp` nehmen eine **"float"** oder **long double** Argument. In einem C-Programm `exp` immer Double und gibt eine **doppelte**.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher C-Header|Erforderlicher C++-Header|  
|--------------|---------------------|---|  
|`exp`, `expf`|\<math.h>|\<cmath> oder \<math.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
exp( 2.302585 ) = 10.000000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [_CIexp](../../c-runtime-library/ciexp.md)