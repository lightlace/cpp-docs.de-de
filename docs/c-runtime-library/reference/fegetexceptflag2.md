---
title: fegetexceptflag2 | Microsoft-Dokumentation
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
- fegetexceptflag
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
- fegetexceptflag
- fenv/fegetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b1180db74e0000f24e12b6d411460e6a4efc9de
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="fegetexceptflag"></a>fegetexceptflag
Speichert den aktuellen Zustand der angegebenen Gleitkommaausnahme-Flags.  
  
## <a name="syntax"></a>Syntax  
  
```  
int fegetexceptflag(   
   fexcept_t* pstatus,   
   int excepts   
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `pstatus`  
 Ein Zeiger auf ein `fexcept_t`-Objekt, das die aktuellen Werte der Ausnahme-Flags enthält, die von `excepts` angegeben sind.  
  
 `excepts`  
 Die in `pstatus` zu speichernden Gleitkommaausnahme-Flags.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg wird 0 zurückgegeben. Andernfalls wird ein Wert ungleich null zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `fegetexceptflag` speichert den aktuellen Zustand der von `excepts` angegebenen Gleitkommaausnahme-Statusflags im `fexcept_t`-Objekt, auf die `pstatus` verweist.  `pstatus` muss auf ein gültiges `fexcept_t`-Objekt zeigen. Andernfalls ist das daraus resultierende Verhalten nicht definiert. Die Funktion `fegetexceptflag` unterstützt diese in \<fenv.h> definierten Ausnahmemakros:  
  
|Ausnahmemakro|Beschreibung|  
|---------------------|-----------------|  
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|  
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|  
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|  
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|  
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|  
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|  
  
 Das Argument `excepts` kann entweder null, eines der unterstützten Gleitkommaausnahme-Makros oder das bitweise OR von mindestens zwei der Makros sein. Der Effekt von jedem anderen Argumentwert ist nicht definiert.  
  
 Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`fegetexceptflag`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)