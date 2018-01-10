---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl | Microsoft-Dokumentation
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
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
- lrint
- lrintf
- lrintl
- llrint
- llrintf
- llrintl
- math/lrint
- math/lrintf
- math/lrintl
- math/llrint
- math/llrintf
- math/llrintl
dev_langs: C++
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2774b22f0b108349d90abc113430f1a573d2cbb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl
Rundet den angegebenen Gleitkommawert auf den nächsten ganzzahligen Wert mit dem aktuellen Rundungsmodus und Richtung.  
  
## <a name="syntax"></a>Syntax  
  
```  
long int lrint(  
   double x  
);  
  
long int lrint(  
   float x  
); //C++ only  
  
long int lrint(  
   long double x  
); //C++ only  
  
long int lrintf(  
   float x  
);  
  
long int lrintl(  
   long double x  
);  
  
long long int llrint(  
   double x  
);  
  
long long int llrint(  
   float x  
); //C++ only  
  
long long int llrint(  
   long double x  
); //C++ only  
  
long long int llrintf(  
   float x  
);  
  
long long int llrintl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `x`  
 Der zu rundende Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg wird der gerundete Integralwert von `x` zurückgegeben.  
  
|Problem|Zurück|  
|-----------|------------|  
|`x` liegt außerhalb des Bereichs des Rückgabetyps.<br /><br /> `x` = ±∞<br /><br /> `x` = NaN|Löst FE_INVALID aus und gibt 0 (null) zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Da C++ Überladungen zulässt, können Sie Überladungen von `lrint` und `llrint` aufrufen, die float- und long double-Typen annehmen. In einem C-Programm verwenden `lrint` und `llrint` immer einen Double.  
  
 Wenn `x` nicht die entsprechende Gleitkommazahl eines Integralwerts darstellt, lösen diese Funktionen FE_INEXACT aus.  
  
 **Microsoft-spezifisch**: Wenn das Ergebnis außerhalb des Bereichs des Rückgabetyps ist oder wenn der Parameter NaN oder unendlich ist, ist der Rückgabewert von der Implementierung abhängig. Der Microsoft-Compiler gibt den Wert 0 (null) zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`lrint`,                `lrintf`, `lrintl`, `llrint`, `llrintf`, `llrintl`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)