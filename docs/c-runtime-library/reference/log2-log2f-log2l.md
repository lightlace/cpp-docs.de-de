---
title: log2, log2f, log2l | Microsoft-Dokumentation
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
- log2
- log2l
- log2f
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
dev_langs: C++
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f825304439e3e1c27f5dc1e41a1ae4c311450625
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l
Bestimmt den binären Logarithmus (Basis 2) des angegebenen Werts.  
  
## <a name="syntax"></a>Syntax  
  
```  
double log2(  
   double x  
);  
  
float log2(  
   float x  
); //C++ only  
  
long double log2(  
   long double x  
); //C++ only  
  
float log2f(  
   float x  
);  
  
long double log2l(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `x`  
 Der Wert, um den Basis 2-Logarithmus zu bestimmen.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg wird log2 `x` zurückgegeben.  
  
 Andernfalls wird einer der folgenden Werte zurückgeben:  
  
|Problem|Zurück|  
|-----------|------------|  
|`x` < 0|NaN|  
|`x` = ±0|-UNENDLICH|  
|`x` = 1|+0|  
|+UNENDLICH|+UNENDLICH|  
|NaN|NaN|  
|Domänenfehler|NaN|  
|pole-Fehler|-HUGE_VAL, -HUGE_VALF, oder -HUGE_VALL|  
  
 Fehler werden gemäß den Angaben in [_matherr](../../c-runtime-library/reference/matherr.md) gemeldet.  
  
## <a name="remarks"></a>Hinweise  
 Ist „x“ eine ganze Zahl, gibt diese Funktion im Wesentlichen den nullbasierten Index des höchstwertigen 1-Bits von `x` zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`log2`,                `log2f`,  `log2l`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp2, exp2f, exp2l](../../c-runtime-library/reference/exp2-exp2f-exp2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)