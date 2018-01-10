---
title: fma, fmaf, fmal | Microsoft-Dokumentation
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
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
dev_langs: C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd4178718380502e91bb7f019164f2398c93323c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal
Multipliziert zwei Werte, addiert einen dritten und rundet das Ergebnis, ohne Genauigkeit aufgrund von vorherigen Rundungen einzubüßen.  
  
## <a name="syntax"></a>Syntax  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `x`  
 Der erste zu multiplizierende Wert.  
  
 [in] `y`  
 Der zweite zu multiplizierende Wert.  
  
 [in] `z`  
 Der hinzuzufügende Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `(x * y) + z`zurück. Der Rückgabewert wird dann mit dem aktuellen Rundungsformat gerundet.  
  
 Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:  
  
|Problem|Zurück|  
|-----------|------------|  
|`x` = INFINITY, `y` = 0 oder<br /><br /> `x` = 0, `y` = INFINITY|NaN|  
|`x`oder `y` = genaue ± UNENDLICH, `z` = UNENDLICH mit umgekehrtem Vorzeichen|NaN|  
|`x` oder `y` = NaN|NaN|  
|nicht (`x` = 0, `y`= indefinite) und `z` = NaN<br /><br /> nicht (`x`=indefinite, `y`=0) und `z` = NaN|NaN|  
|Überlaufbereichsfehler|±HUGE_VAL, ±HUGE_VALF oder ±HUGE_VALL|  
|Unterlaufbereichsfehler|Richtige Wert nach dem Runden|  
  
 Fehler werden gemäß der Angaben in [_matherr](../../c-runtime-library/reference/matherr.md) gemeldet.  
  
## <a name="remarks"></a>Hinweise  
 Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen `fma` verwenden und zurückgeben **"float"** und **long double** Typen. In einem C-Programm `fma` immer Double und gibt eine **doppelte**.  
  
 Diese Funktion berechnet den Wert mit unendlicher Genauigkeit und rundet das endgültige Ergebnis dann.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`fma`, `fmaf`, `fmal`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)