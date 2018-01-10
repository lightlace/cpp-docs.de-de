---
title: feraiseexcept | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: feraiseexcept
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
apitype: HeaderDef
f1_keywords:
- feraiseexcept
- fenv/feraiseexcept
dev_langs: C++
helpviewer_keywords: feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ab77da8cee422bab618dc8737ad254b65301ffd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="feraiseexcept"></a>feraiseexcept
Löst die angegebenen Gleitkommaausnahmen aus  
  
## <a name="syntax"></a>Syntax  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `excepts`  
 Die auszulösenden Gleitkommaausnahmen  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn alle angegebenen Ausnahmen erfolgreich ausgelöst werden, wird 0 zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `feraiseexcept` versucht, die von `excepts` angegebenen Gleitkommaausnahmen auszulösen.   Die Funktion `feraiseexcept` unterstützt diese in \<fenv.h> definierten Ausnahmemakros:  
  
|Ausnahmemakro|Beschreibung|  
|---------------------|-----------------|  
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|  
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|  
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|  
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|  
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|  
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|  
  
 Das Argument `excepts` kann entweder 0, einer der Ausnahmemakrowerte oder das bitweise OR von mindestens zwei der unterstützten Ausnahmemakros sein. Wenn eines der angegebenen Ausnahmemakros FE_OVERFLOW oder FE_UNDERFLOW ist, kann die Ausnahme FE_INEXACT als Nebeneffekt ausgelöst werden.  
  
 Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).  
  
 **Microsoft Specific:** Die in `excepts` angegebenen Ausnahmen werden in der Reihenfolge FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT ausgelöst. FE_INEXACT kann allerdings ausgelöst werden, wenn FE_OVERFLOW oder FE_UNDERFLOW ausgelöst wird, selbst wenn dies nicht in `excepts` angegebenen ist. **End Microsoft Specific**  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`feraiseexcept`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)