---
title: Fmin, Fminf, Fminl | Microsoft-Dokumentation
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
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
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
translationtype: Machine Translation
ms.sourcegitcommit: 8953e3bd81158ce183e1abb5dfa969164c1f9ced
ms.openlocfilehash: b7fd6a2b91c1bc7cd973d2ac60f2d6fc39d322bb
ms.lasthandoff: 02/24/2017

---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl
Bestimmt den kleineren von zwei angegebenen Werten.  
  
## <a name="syntax"></a>Syntax  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Der erste zu vergleichende Wert.  
  
 `y`  
 Der zweite zu vergleichende Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung wird der kleinere der Werte `x` oder `y` zurückgegeben.  
  
|Eingabe|Ergebnis|  
|-----------|------------|  
|`x` ist NaN|`y`|  
|`y` ist NaN|`x`|  
|`x` und `y` sind NaN|NaN|  
  
 Die Funktion ruft weder den Aufruf von [_matherr](../../c-runtime-library/reference/matherr.md) auf, noch löst sie Gleitkommaausnahmen aus oder ändert den Wert `errno`.  
  
## <a name="remarks"></a>Hinweise  
 Da C++ Überladungen zulässt, können Sie Überladungen von `fmin` aufrufen, die float- und long double-Typen annehmen und zurückgeben. In einem C-Programm verwendet `fmin` immer double und gibt auch double zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`fmin`, `fminf`, `fminl`|C: \<math.h><br />C++: \<math.h> oder \<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)  
 [fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)  
