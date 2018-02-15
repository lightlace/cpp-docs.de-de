---
title: fpclassify | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81a2c9c5237d455908e1d0e4f58bff87418a7f8b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="fpclassify"></a>fpclassify
Gibt die Gleitkommaklassifizierung des Arguments zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Der zu testende Gleitkommawert.  
  
## <a name="return-value"></a>Rückgabewert  
 `fpclassify` gibt einen ganzzahligen Wert zurück, der die Gleitkommaklasse des Arguments `x` angibt. Diese Tabelle zeigt die in \<math.h> definierten möglichen Rückgabewerte von `fpclassify`.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`FP_NAN`|Ein stiller, signalisierender oder unbestimmter NaN|  
|`FP_INFINITE`|Eine positive oder negative Unendlichkeit|  
|`FP_NORMAL`|Ein positiver oder negativer ungleich null normalisierter Wert|  
|`FP_SUBNORMAL`|Ein positiver oder negativer denormalisierter Wert|  
|`FP_ZERO`|Ein positiver oder negativer Nullwert|  
  
## <a name="remarks"></a>Hinweise  
 In C ist `fpclassify` ein Makro. In C++ ist `fpclassify` eine Funktion, die mithilfe der Argumenttypen `float`, `double` oder `long double` überladen wird. In beiden Fällen hängt der zurückgegebene Wert vom tatsächlichen Typ des Argumentausdrucks ab, und nicht von einer Zwischendarstellung. Ein normaler `double`- oder `long double`-Wert kann z.B. unendlich, nicht normal oder ein Nullwert werden, wenn er in `float` konvertiert wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion/Makro|Erforderlicher Header (C)|Erforderlicher Header (C++)|  
|---------------------|---------------------------|-------------------------------|  
|`fpclassify`|\<math.h>|\<math.h> oder \<cmath>|  
  
 Der Makro `fpclassify` und die Funktionen `fpclassify` entsprechen den C99- und C++11-Spezifikationen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)