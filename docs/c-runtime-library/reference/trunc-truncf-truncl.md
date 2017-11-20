---
title: trunc, truncf, truncl | Microsoft-Dokumentation
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
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
dev_langs: C++
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2a78deabb758a7d8fe8b0da61899bf7ad11dd8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl
Bestimmt die nächste ganze Zahl, die kleiner oder gleich dem angegebenen Gleitkommawert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `x`  
 Der abzuschneidende Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt bei erfolgreicher Ausführung einen ganzzahligen Wert von `x` in Richtung null gerundet zurück.  
  
 Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:  
  
|Problem|Zurück|  
|-----------|------------|  
|`x` = ±INFINITY|w|  
|`x` =  ±0|w|  
|`x` = NaN|NaN|  
  
 Fehler werden gemäß der Angaben in [_matherr](../../c-runtime-library/reference/matherr.md) gemeldet.  
  
## <a name="remarks"></a>Hinweise  
 Da C++ Überladungen zulässt, können Sie Überladungen von `trunc` aufrufen, die float- und long double-Typen annehmen und zurückgeben. In einem C-Programm verwendet `trunc` immer double und gibt auch double zurück.  
  
 Da die größten Gleitkommawerte exakte ganze Zahlen sind, wird diese Funktion nicht eigenständig überlaufen. Sie können diese Funktion jedoch möglicherweise bei der Rückgabe eines Werts in einen ganzzahligen Typ zum Überlaufen bringen.  
  
 Sie können auch abrunden, indem Sie Gleitkommazahlen implizit in ganzzahlige konvertieren. Dies ist jedoch nur für die Werte möglich, die im Zieltyp gespeichert werden können.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`trunc`,                `truncf`,  `truncl`|\<math.h>|\<cmath>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Funktionsreferenz (alphabetisch)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)