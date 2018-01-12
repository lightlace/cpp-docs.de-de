---
title: log1p, log1pf, log1pl2 | Microsoft-Dokumentation
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
- log1p
- log1pf
- log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f32799e2eabc54dacdc5144c59483b7a6a641110
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl
Berechnet den natürlichen Logarithmus von 1 plus den angegebenen Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```  
double log1p(  
   double x  
);  
  
float log1p(  
   float x  
); //C++ only  
  
long double log1p(  
   long double x  
); //C++ only  
  
float log1pf(  
   float x  
);  
  
long double log1pl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Das Gleitkommaargument.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg wird der natürliche Logarithmus (Basis e) von (`x`+ 1) zurückgegeben.  
  
 Andernfalls wird einer der folgenden Werte zurückgeben:  
  
|Eingabe|Ergebnis|SEH-Ausnahme|errno|  
|-----------|------------|-------------------|-----------|  
|+inf|+inf|||  
|Abbrüche|Identisch mit der Eingabe|UNDERFLOW||  
|±0|Identisch mit der Eingabe|||  
|-1|-inf|DIVBYZERO|ERANGE|  
|< -1|nan|INVALID|EDOM|  
|-inf|nan|INVALID|EDOM|  
|±SNaN|Identisch mit der Eingabe|INVALID||  
|±QNaN unbestimmtes|Identisch mit der Eingabe|||  
  
 Der `errno`-Wert wird auf ERANGE festgelegt, wenn `x`=1. Die `errno` Wert auf EDOM festgelegt wird, wenn `x` <-1 zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `log1p`-Funktionen sind möglicherweise genauer als log(`x`+ 1) wenn X nahe 0 ist.  
  
 Da C++ Überladungen zulässt, können Sie Überladungen von `log1p` aufrufen, die float- und long double-Typen annehmen und zurückgeben. In einem C-Programm verwendet `log1p` immer double und gibt auch double zurück.  
  
 Wenn `x` eine natürliche Zahl ist, gibt diese Funktion den Logarithmus der Fakultät (`x`-1) zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`log1p`,                `log1pf`,  `log1pl`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)