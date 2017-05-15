---
title: exp2, exp2f, exp2l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- exp2
- exp2f
- exp2l
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
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
dev_langs:
- C++
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 4c3e31359c096dddfc7d71dcd7887c405b9aa0af
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l
Berechnet die 2, die ausgelöst wird, auf den angegebenen Wert.  
  
## <a name="syntax"></a>Syntax  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `x`  
 Der Wert des Exponenten.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg gibt der Exponent zur Basis-2 `x`, d. h. 2<sup>x</sup>. Andernfalls gibt einen der folgenden Werte zurück:  
  
|Problem|Zurück|  
|-----------|------------|  
|`x` = ±0|1|  
|`x` = -INFINITY|+0|  
|`x` = +INFINITY|+INFINITY|  
|`x` = NaN|NaN|  
|Überlaufbereichsfehler|+HUGE_VAL, +HUGE_VALF, oder +HUGE_VALL|  
|Unterlaufbereichsfehler|Korrekte Ergebnis, nach dem runden|  
  
 Fehler werden gemäß den Angaben in [_matherr](../../c-runtime-library/reference/matherr.md) gemeldet.  
  
## <a name="remarks"></a>Hinweise  
 Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen `exp2` verwenden und zurückgeben **"float"** und **long double** Typen. In einem C-Programm `exp2` immer Double und gibt eine **doppelte**.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|C-Header|C++-Header|  
|-------------|--------------|------------------|  
|`exp`, `expf`, `expl`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [EXP, Expf, expl](../../c-runtime-library/reference/exp-expf.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)
