---
title: erf, erff, erfl, erfc, erfcf, erfcl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- erff
- erfl
- erf
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
- erfl
- erf
- erff
dev_langs:
- C++
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 78c12c22f85eb9ba50b1ea5a92f6f3bb171e01a0
ms.lasthandoff: 02/24/2017

---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl
Berechnet die Fehlerfunktion oder die komplementäre Fehlerfunktion eines Werts.  
  
## <a name="syntax"></a>Syntax  
  
```  
double erf(  
   double x  
);  
float erf(  
   float x  
); // C++ only  
long double erf(  
   long double x  
); // C++ only  
float erff(  
   float x  
);  
long double erfl(  
   long double x  
);  
double erfc(  
   double x  
);  
float erfc(  
   float x  
); // C++ only  
long double erfc(  
   long double x  
); // C++ only  
float erfcf(  
   float x  
);  
long double erfcl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Ein Gleitkommawert.  
  
## <a name="return-value"></a>Rückgabewert  
 Die `erf`-Funktionen geben die Gauß-Fehlerfunktion von `x` zurück. Die `erfc`-Funktionen geben die komplementäre Gauß-Fehlerfunktion von `x` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `erf`-Funktionen berechnen die Gauß-Fehlerfunktion von x, die wie folgt definiert ist:  
  
 ![Die Fehlerfunktion von x](../../c-runtime-library/reference/media/crt_erf_formula.PNG "CRT_erf_formula")  
  
 Die komplementäre Gauß-Fehlerfunktion ist als 1 - erf(x) definiert. Die `erf`-Funktionen geben einen Wert im Bereich -1,0 bis 1,0 zurück. Es gibt keine Fehlerrückgabe. Die `erfc`-Funktionen geben einen Wert im Bereich 0 bis 2 zurück. Wenn `x` für `erfc` zu groß ist, wird die `errno`-Variable auf `ERANGE` festgelegt.  
  
 Da C++ das Überladen zulässt, können Sie Überladungen von `erf` und `erfc` aufrufen, die `float`- und `long double`-Typen verwenden und zurückgeben. In einem C-Programm verwenden `erf` und `erfc` immer `double` und geben dieses auch zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`erf`, `erff`, `erfl`, `erfc`, `erfcf`, `erfcl`|\<math.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)
