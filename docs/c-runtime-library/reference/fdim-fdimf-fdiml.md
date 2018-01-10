---
title: fdim, fdimf, fdiml | Microsoft-Dokumentation
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
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
dev_langs: C++
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ecf0b0590942aad133cb7b8f478200525e4f4519
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml
Bestimmt den positiven Unterschied zwischen den ersten und zweiten Werten.  
  
## <a name="syntax"></a>Syntax  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `x`  
 Der erste Wert.  
  
 [in] `y`  
 Der zweite Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den positiven Unterschied zwischen `x` und `y` zurück:  
  
|Rückgabewert|Szenario|  
|------------------|--------------|  
|x-y|wenn x > y|  
|0|wenn x <= y|  
  
 Andernfalls wird einer der folgenden Fehler zurückgeben:  
  
|Problem|Zurück|  
|-----------|------------|  
|Überlaufbereichsfehler|+HUGE_VAL, +HUGE_VALF, oder +HUGE_VALL|  
|Unterlaufbereichsfehler|Richtiger Wert (nach dem Runden)|  
|`x` oder `y` ist NaN|NaN|  
  
 Fehler werden gemäß der Angaben in [_matherr](../../c-runtime-library/reference/matherr.md) gemeldet.  
  
## <a name="remarks"></a>Hinweise  
 Da C++ Überladungen zulässt, können Sie Überladungen von `fdim` aufrufen, die float- und long double-Typen annehmen und zurückgeben. In einem C-Programm verwendet `fdim` immer double und gibt auch double zurück.  
  
 Diese Funktion entspricht, mit Ausnahme der Behandlung "NaN" `fmax(x - y, 0)`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`fdim`, `fdimf`, `fdiml`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [abs, labs, llabs, _abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)