---
title: fegetround, fesetround2| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fegetround
- fesetround
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
dev_langs:
- C++
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf50371c781a5ade76f3f35de8fc760331d72a20
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="fegetround-fesetround"></a>fegetround, fesetround
Ruft den aktuellen Gleitkomma-Rundungsmodus ab bzw. legt ihn fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
int fegetround(void);  
  
int fesetround(  
   int round_mode  
);   
```  
  
#### <a name="parameters"></a>Parameter  
 `round_mode`  
 Der als eines der Gleitkomma-Rundungsmakros festzulegende Rundungsmodus. Wenn der Wert keinem der Gleitkomma-Rundungsmakros entspricht, wird der Rundungsmodus nicht geändert.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg gibt `fegetround` den Rundungsmodus als einen der Gleitkomma-Rundungsmakrowerte zurück. Ein negativer Wert wird zurückgegeben, wenn der aktuelle Rundungsmodus nicht bestimmt werden kann.  
  
 Bei Erfolg gibt `fesetround` 0 (null) zurück. Andernfalls wird ein Wert ungleich null zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Gleitkommaoperationen können mehrere Rundungsmodi verwenden. Diese steuern, in welche Richtung die Ergebnisse von Gleitkommaoperationen beim Speichern der Ergebnisse gerundet werden. Hiermit werden die Namen und das Verhalten der in \<<fenv.h> definierten Gleitkomma-Rundungsmakros angegeben:  
  
|Makro|Beschreibung|  
|-----------|-----------------|  
|FE_DOWNWARD|Runden in Richtung minus unendlich.|  
|FE_TONEAREST|Runden in Richtung des nächsten Werts.|  
|FE_TOWARDZERO|Runden in Richtung 0 (null).|  
|FE_UPWARD|Runden in Richtung plus unendlich.|  
  
 Das Standardverhalten von FE_TONEAREST ist, Ergebnisse in der Mitte zwischen darstellbaren Werten auf den nächsten Wert mit einem geraden (0) LSB (Least Significant Bit, niedrigstwertiges Bit) zu runden.  
  
 Der aktuelle Rundungsmodus wirkt sich auf diese Vorgänge aus:  
  
-   Zeichenfolgenkonvertierungen.  
  
-   Die Ergebnisse der arithmetischen Gleitkommaoperatoren außerhalb konstanter Ausdrücke.  
  
-   Die Rundungsfunktionen der Bibliothek, wie z. B. `rint` und `nearbyint`.  
  
-   Rückgabewerte aus mathematischen Funktionen der Standardbibliothek.  
  
 Der aktuelle Rundungsmodus wirkt sich auf diese Vorgänge nicht aus:  
  
-   Die Bibliotheksfunktionen `trunc`, `ceil`, `floor`und `lround` .  
  
-   Implizite Umwandlungen und Konvertierungen von Gleitkommazahl in ganze Zahl, bei denen immer in Richtung 0 (null) gerundet wird.  
  
-   Die Ergebnisse von arithmetischen Gleitkommaoperatoren in konstanten Ausdrücken, bei denen immer auf den nächsten Wert gerundet wird.  
  
 Um diese Funktionen zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)` -Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`fegetround`,                `fesetround`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [nearbyint, nearbyintf, nearbyintl](../../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)   
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](../../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)