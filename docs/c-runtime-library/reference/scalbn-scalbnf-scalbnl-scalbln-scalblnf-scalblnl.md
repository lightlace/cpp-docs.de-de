---
title: scalbn scalbnf, scalbnl, scalbln, scalblnf, scalblnl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
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
- scalblnf
- scalbnl
- scalblnl
- scalbln
- scalbn
- scalbnf
dev_langs:
- C++
helpviewer_keywords:
- scalbn function
- scalbln function
- scalblnl function
- scalbnl function
- scalbnf function
- scalblnf function
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: 5
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 1c2e10f5836dc27475f76d4b94cf32e17f52e1a5
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl"></a>scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
Multipliziert eine Gleitkommazahl mit einer ganzzahligen Potenz von FLT_RADIX.  
  
## <a name="syntax"></a>Syntax  
  
```  
double scalbn(  
   double x,  
   int exp   
);  
float scalbn(  
   float x,  
   int exp  
);  // C++ only  
long double scalbn(  
   long double x,  
   int exp  
);  // C++ only   
float scalbnf(  
   float x,  
   int exp  
);   
long double scalbnl(  
   long double x,  
   int exp  
);  
double scalbln(  
   double x,  
   long exp   
);  
float scalbln(  
   float x,  
   long exp  
);  // C++ only  
long double scalbln(  
   long double x,  
   long exp  
);  // C++ only   
float scalblnf(  
   float x,  
   long exp  
);   
long double scalblnl(  
   long double x,  
   long exp  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Gleitkommawert.  
  
 `exp`  
 Ganzzahlexponent.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg gibt die `scalbn`-Funktion den Wert von `x` * `FLT_RADIX`<sup>exp</sup> zurück. Bei einem Überlauf (abhängig vom Vorzeichen des `x`), `scalbn` gibt `HUGE_VAL`; das `errno` Wert wird festgelegt, um `ERANGE`.  
  
 Weitere Informationen zu `errno` und mögliche Fehlerrückgabewerte finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 `FLT_RADIX` ist in \<float.h> als native Gleitkommabasis definiert; in binären Systemen hat es den Wert 2, und `scalbn` entspricht [ldexp](../../c-runtime-library/reference/ldexp.md).  
  
 Da C++ das Überladen zulässt, können Sie Überladungen von `scalbn` und `scalbln` aufrufen, die `float`- oder `long double`-Typen verwenden und zurückgeben. In einem C-Programm verwendet `scalbn` immer `double` und `int` und gibt `double` zurück, und `scalbln` verwendet immer `double` und `long` und gibt `double` zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`scalbn`, `scalbnf`, `scalbnl`, `scalbln`, `scalblnf`, `scalblnl`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_scalbn.c  
// Compile using: cl /W4 crt_scalbn.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 6.4, y;  
   int p = 3;  
  
   y = scalbn( x, p );  
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
6.4 times FLT_RADIX to the power of 3 is 51.2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)
