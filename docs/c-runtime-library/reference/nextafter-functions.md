---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
dev_langs: C++
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 798e39624c617d8178a7598e74451ca2851cfe12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
Gibt den nächsten darstellbaren Gleitkommawert zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Der Gleitkommawert, der den Startpunkt markiert.  
  
 `y`  
 Der Gleitkommawert, der den Zielpunkt markiert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den nächsten darstellbaren Gleitkommawert des Rückgabetyps nach `x` in Richtung `y` an. Wenn `x`=`y`, gibt die Funktion den in den Rückgabetyp konvertierten Wert `y` zurück, ohne eine Ausnahme auszulösen. Wenn `x` ungleich `y` und das Ergebnis eine subnormale Zahl oder 0 (null) ist, werden die Gleitkomma-Ausnahmezustände FE_UNDERFLOW und FE_INEXACT festgelegt, und das richtige Ergebnis wird zurückgegeben. Wenn `x` oder `y` eine NaN ist, dann entspricht der Rückgabewert einer der Eingabe-NaN. Wenn `x` begrenzt und das Ergebnis unendlich oder nicht als der jeweilige Typ darstellbar ist, wird eine Unendlichkeit oder NaN mit den richtigen Vorzeichen zurückgegeben. Des Weiteren werden die Gleitkomma-Ausnahmezustände FE_UNDERFLOW und FE_INEXACT festgelegt, und für `errno` wird ERANGE festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die `nextafter` und `nexttoward`-Funktionsfamilien sind mit Ausnahme des Parametertyps von `y` gleichwertig. Wenn `x` und `y` identisch sind, ist der zurückgegebene Wert `y`. Dieser wird in den Rückgabetyp konvertiert.  
  
 Da C++ das Überladen zulässt, können Sie \<cmath> verwenden und so Überladungen von `nextafter` und `nexttoward` aufrufen, die die Typen `float` und `long double` zurückgeben. In einem C-Programm geben `nextafter` und `nexttoward` immer `double` zurück.  
  
 Die Funktionen `_nextafter` und `_nextafterf` sind Microsoft-spezifisch. Die `_nextafterf`-Funktion ist nur verfügbar, wenn für x64 kompiliert wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|  
|-------------|---------------------------|-------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h>|\<math.h> oder \<cmath>|  
|`_nextafter`|\<float.h>|\<float.h> oder \<cfloat>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)