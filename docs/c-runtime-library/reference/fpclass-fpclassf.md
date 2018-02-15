---
title: _fpclass, _fpclassf | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fpclass
- _fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a13abc84cf3e28f6282bf5c160d118d019334cfd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf
Gibt einen Wert zurück, der die Gleitkommaklassifizierung des Arguments angibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Der zu testende Gleitkommawert.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Funktionen `_fpclass` und `_fpclassf` geben einen ganzzahligen Wert zurück, der die Gleitkommaklassifizierung des Arguments `x` angibt. Die Klassifizierung weist möglicherweise einen der folgenden, in \<float.h> definierten Werte auf.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`_FPCLASS_SNAN`|Signalisierender NaN|  
|`_FPCLASS_QNAN`|Stiller NaN|  
|`_FPCLASS_NINF`|Minus unendlich (-INF)|  
|`_FPCLASS_NN`|Negativ normalisierter ungleich null-Wert|  
|`_FPCLASS_ND`|Negativ denormalisiert|  
|`_FPCLASS_NZ`|Negative 0 (null) (– 0)|  
|`_FPCLASS_PZ`|Positiv 0 (+0)|  
|`_FPCLASS_PD`|Positiv denormalisiert|  
|`_FPCLASS_PN`|Positiv normalisierter ungleich null-Wert|  
|`_FPCLASS_PINF`|Positiv unendlich|  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen `_fpclass` und `_fpclassf` sind Microsoft-spezifisch. Sie ähneln [fpclassify](../../c-runtime-library/reference/fpclassify.md), geben jedoch detaillierte Informationen über das Argument zurück. Die `_fpclassf`-Funktion ist nur verfügbar, wenn sie für die x64-Plattform kompiliert wurde.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`_fpclass`|\<float.h>|  
  
 Weitere Informationen zur Kompatibilität und Konformität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)