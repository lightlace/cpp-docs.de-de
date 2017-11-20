---
title: _finite, _finitef | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _finite
- _finitef
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
dev_langs: C++
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cb08c6a525222e8c1bb886f87aa55b2996cd3846
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="finite-finitef"></a>_finite, _finitef
Bestimmt, ob ein Gleitkommawert endlich ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Der zu testende Gleitkommawert.  
  
## <a name="return-value"></a>Rückgabewert  
 Sowohl `_finite` und `_finitef` einen Wert ungleich NULL zurück, wenn das Argument *x* endlich; d. h., wenn – INF < `x` < + INF. 0 (null), wenn das Argument unendlich oder ein NaN-Wert ist.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `_finite` und `_finitef` sind Microsoft-spezifisch. Die Funktion `_finitef` ist nur verfügbar, wenn sie für x86, ARM- oder ARM64-Plattformen kompiliert wurde.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header (C)|Erforderlicher Header (C++)|  
|--------------|---------------------------|-------------------------------|  
|`_finite`|\<float.h> or \<math.h>|\<float.h>, \<math.h>, \<cfloat>, or \<cmath>|  
|`_finitef`|\<math.h>|\<math.h> or \<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)