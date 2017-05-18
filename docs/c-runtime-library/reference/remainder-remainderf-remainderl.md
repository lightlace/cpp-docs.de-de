---
title: remainder, remainderf, remainderl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
dev_langs:
- C++
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 8
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
ms.openlocfilehash: bfd25184e2542c8f1f3c4e1e975397685328b64b
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl
Berechnet den Rest des Quotienten aus zwei Gleitkommawerten, gerundet auf den nächsten ganzzahligen Wert.  
  
## <a name="syntax"></a>Syntax  
  
```  
double remainder(   
   double numer,  
   double denom  
);  
float remainder(   
   float numer,  
   float denom  
); /* C++ only */  
long double remainder(   
   long double numer,  
   long double denom  
); /* C++ only */  
float remainderf(   
   float numer,  
   float denom  
);  
long double remainderl(   
   long double numer,  
   long double denom  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `numer`  
 Der Zähler.  
  
 `denom`  
 Der Nenner.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Gleitkommarest von `x` / `y`. Wenn der Wert von `y` 0,0 ist, gibt `remainder` ein stilles NaN zurück. Informationen über die Darstellung eines stillen NaN durch die `printf`-Familie finden Sie unter [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `remainder`-Funktion berechnet den Gleitkommarest `r` von `x` / `y`, sodass `x` = `n` * `y` + `r`, wobei `n` die am nächsten liegende ganze Zahl zum Wert `x` / `y` ist, und `n` gerade ist, wenn &#124; `n` - `x` / `y` &#124; = 1/2. Wenn `r` = 0 ist, hat `r` das gleiche Vorzeichen wie `x`.  
  
 Da C++ das Überladen zulässt, können Sie Überladungen von `remainder` aufrufen, die `float` oder `long double`-Werte verwenden und zurückgeben. In einem C-Programm verwendet `remainder` immer zwei Double und gibt einen Double zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`remainder`, `remainderf`, `remainderl`|\<math.h>|  
  
 Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_remainder.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = remainder(w, x);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
}  
```  
  
```Output  
The remainder of -10.00 / 3.00 is -1.000000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)
