---
title: nearbyint, nearbyintf, nearbyintl1 | Microsoft-Dokumentation
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
- nearbyint
- nearbyintf
- nerabyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
dev_langs: C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d95f92d15dcf4b8baf84b762b994bdb52930346d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl
Rundet den angegebenen Gleitkommawert auf eine ganze Zahl und gibt diesen Wert in einem Gleitkommaformat zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `x`  
 Der zu rundende Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `x` bei erfolgreicher Ausführung auf die nächste ganze Zahl gerundet zurück. Die Funktion verwendet dafür das von „fegetround“ definierte aktuelle Rundungsformat. Andernfalls gibt die Funktion möglicherweise einen der folgenden Werte zurück:  
  
|Problem|Zurück|  
|-----------|------------|  
|`x`= ±INFINITY|±Infinity, unverändert bleiben sollen|  
|`x` = ±0|±0, unverändert bleiben sollen|  
|`x` = NaN|NaN|  
  
 Fehler werden nicht über [_matherr](../../c-runtime-library/reference/matherr.md) gemeldet. Diese Funktion meldet vor allem keine FE_INEXACT-Ausnahmen.  
  
## <a name="remarks"></a>Hinweise  
 Der Hauptunterschied zwischen dieser Funktion und `rint` besteht darin, dass diese Funktion keine ungenaue Gleitkommaausnahme auslöst.  
  
 Da die maximalen Gleitkommawerte genaue ganze Zahlen sind, überläuft diese Funktion nie von selbst. Stattdessen ist es möglich, dass der Rückgabewert je nach Version der verwendeten Funktion von der Ausgabe überlaufen wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`nearbyint`,                `nearbyintf`,  `nearbyintl`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)