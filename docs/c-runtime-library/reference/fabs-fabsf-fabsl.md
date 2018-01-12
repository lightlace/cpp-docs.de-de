---
title: fabs, fabsf, fabsl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fabsf
- fabs
- fabsl
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
- fabs
- fabsf
- fabsl
- "math\fabs"
- "math\fabsf"
- "math\fabsl"
dev_langs: C++
helpviewer_keywords:
- absolute values
- fabsf function
- calculating absolute values
- fabs function
- fabsl function
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: acf1c5f64251c97091cef00d4fa6345e1f46de53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fabs-fabsf-fabsl"></a>fabs, fabsf, fabsl
Berechnet den absoluten Wert des Gleitkommaarguments.  
  
## <a name="syntax"></a>Syntax  
  
```  
double fabs(   
   double x   
);  
float fabs(  
   float x   
); // C++ only  
long double fabs(  
   long double x  
); // C++ only  
float fabsf(   
   float x   
);  
long double fabsl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `x`  
 Gleitkommawert.  
  
## <a name="return-value"></a>Rückgabewert  
 Die `fabs`-Funktionen geben den absoluten Wert des Arguments `x` zurück. Es gibt keine Fehlerrückgabe.  
  
|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|  
|-----------|-------------------|-----------------------|  
|± QNAN,IND|Keine|_DOMAIN|  
  
## <a name="remarks"></a>Hinweise  
 Da C++ das Überladen zulässt, können Sie Überladungen von `fabs` aufrufen, wenn Sie den header \<cmath> einschließen. In einem C-Programm verwendet `fabs` immer double und gibt auch double zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher C-Header|Erforderlicher C++-Header|  
|--------------|-----------------------|---------------------------|  
|`fabs`, `fabsf`, `fabsl`|\<math.h>|\<cmath> oder \<math.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [abs](../../c-runtime-library/reference/abs-labs-llabs-abs64.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [abs, labs, llabs, _abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [_cabs](../../c-runtime-library/reference/cabs.md)   