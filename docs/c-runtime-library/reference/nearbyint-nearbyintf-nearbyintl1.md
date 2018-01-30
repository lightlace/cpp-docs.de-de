---
title: Nearbyint, Nearbyintf, Nearbyintl | Microsoft Docs
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
dev_langs:
- C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d981df622450ef0b52a9b0d81427497a3e180bc
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2018
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
|`x` = ±INFINITY|±Infinity, unverändert bleiben sollen|  
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