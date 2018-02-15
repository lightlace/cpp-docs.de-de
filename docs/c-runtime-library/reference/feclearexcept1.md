---
title: feclearexcept1 | Microsoft-Dokumentation
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
- feclearexcept
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
- feclearexcept
- fenv/feclearexcept
dev_langs:
- C++
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 661e93b181005acbd822fbb3ea2a2f970bbedf3d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="feclearexcept"></a>feclearexcept
Versucht, die Gleitkommaausnahme-Flags zu löschen, die durch das Argument angegeben wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `excepts`  
 Die zu löschenden Gleitkommaausnahme-Flags.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt null zurück, wenn `excepts` null ist, oder wenn alle angegebenen Ausnahmen erfolgreich gelöscht wurden. Andernfalls wird ein Wert ungleich null zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `feclearexcept` versucht, die von `excepts` angegebenen Gleitkommaausnahme-Flags zu löschen. Die Funktion unterstützt diese in fenv.h> definierten Ausnahmemakros:  
  
|Ausnahmemakro|Beschreibung|  
|---------------------|-----------------|  
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|  
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|  
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|  
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|  
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|  
|FE_ALLEXCEPT|Bitweises OR oder alle unterstützten Gleitkommaausnahmen.|  
  
 Das Argument `excepts` kann entweder Null oder das bitweise OR von mindestens einem der unterstützten Ausnahmemakros sein. Das Ergebnis von jedem anderen Argumentwert ist nicht definiert.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`feclearexcept`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)