---
title: logb, logbf, logbl, _logb, _logbf | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- logb
- _logb
- _logbl
- logbf
- logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
dev_langs: C++
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81d44f12b363cf74efd334e8ff7daadb4fee5036
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="logb-logbf-logbl-logb-logbf"></a>logb, logbf, logbl, _logb, _logbf
Extrahiert den Exponentenwert eines Gleitkommaarguments.  
  
## <a name="syntax"></a>Syntax  
  
```  
double logb(  
   double x   
);  
float logb(  
   float x   
); // C++ only  
long double logb(  
   long double x   
); // C++ only   
float logbf(  
   float x   
);  
long double logbl(  
   long double x   
);  
double _logb(  
   double x   
);  
float _logbf(  
   float x   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 w  
 Ein Gleitkommawert.  
  
## <a name="return-value"></a>Rückgabewert  
 `logb` gibt den zufälligen Exponentenwert von `x` als ganze Zahl mit Vorzeichen zurück, dargestellt als Gleitkommawert.  
  
## <a name="remarks"></a>Hinweise  
 Die `logb`-Funktionen extrahieren den Exponentialwert des Gleitkommaarguments `x` so, als dass `x` mit unbegrenztem Bereich dargestellt würde. Ein denormalisiertes Argument `x` wird wie ein normalisiertes behandelt.  
  
 Da C++ das Überladen zulässt, können Sie Überladungen von `logb` aufrufen, die `float` oder `long double`-Werte verwenden und zurückgeben. In einem C-Programm verwendet `logb` immer `double` und gibt diesen Wert zurück.  
  
|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|  
|-----------|-------------------|-----------------------|  
|± QNAN,IND|Keine|_DOMAIN|  
|± 0|ZERODIVIDE|_SING|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_logb`|\<float.h>|  
|`logb`, `logbf`, `logbl`, `_logbf`|\<math.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)