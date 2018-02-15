---
title: isnan, _isnan, _isnanf | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isnan
- _isnanf
- isnan
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
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
dev_langs:
- C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10d0997b1a6b304634c612f0f1615a059fd812b2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="isnan-isnan-isnanf"></a>isnan, _isnan, _isnanf
Testet, ob ein Gleitkommawert keine Zahl ist (NAN).  
  
## <a name="syntax"></a>Syntax  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### <a name="parameters"></a>Parameter  
 *w*  
 Der zu testende Gleitkommawert.  
  
## <a name="return-value"></a>Rückgabewert  
 In C geben das `isnan`-Makro und die `_isnan` und `_isnanf`- Funktionen einen Wert ungleich null zurück, wenn das Argument `x` ein NAN ist; andernfalls geben sie 0 zurück.  
  
 In C++ geben die `isnan`-Vorlagenfunktionen `true` zurück, wenn das Argument `x` ein NAN ist; andernfalls geben sie `false` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Das C-Makro `isnan` und die `_isnan`- und `_isnanf`-Funktionen testen den Gleitkommawert *x*, der einen Wert ungleich null zurückgibt, wenn *x* kein Zahlenwert (NAN) ist. Ein NAN-Wert wird generiert, wenn das Ergebnis einer Gleitkommaoperation nicht im IEEE-754 Gleitkommaformat für den angegebenen Typ dargestellt werden kann. Informationen darüber, wie ein NAN für die Ausgabe dargestellt wird, erhalten Sie unter [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 Wenn als C++ kompiliert, ist das `isnan`-Makro nicht definiert und stattdessen eine `isnan`-Vorlagenfunktion. Sie gibt einen Wert vom Typ `bool` anstelle einer Ganzzahl zurück.  
  
 Die Funktionen `_isnan` und `_isnanf` sind Microsoft-spezifisch. Die `_isnanf`-Funktion ist nur verfügbar, wenn für x64 kompiliert.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|  
|-------------|---------------------------|-------------------------------|  
|`isnan`, `_isnanf`|\<math.h>|\<math.h> oder \<cmath>|  
|`_isnan`|\<float.h>|\<float.h> oder \<cfloat>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [_finite, _finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)