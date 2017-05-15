---
title: fesetexceptflag2 | Microsoft-Dokumentation
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
- fesetexceptflag
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
- fesetexceptflag
- fenv/fesetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 2283d258a15fb131367d5d24a921c0a84a31e91d
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="fesetexceptflag"></a>fesetexceptflag
Legt die angegebenen Gleitkomma-Statusflags in der aktuellen Gleitkommaumgebung fest  
  
## <a name="syntax"></a>Syntax  
  
```  
int fesetexceptflag(  
     const fexcept_t *pstatus,  
     int excepts  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pstatus`  
 Zeiger auf ein `fexcept_t`-Objekt, das die Werte enthält, auf die die Ausnahmestatusflags festgelegt werden sollen. Das Objekt kann auf einen früheren Aufruf von [fegetexceptflag](fegetexceptflag2.md) festgelegt werden .  
  
 `excepts`  
 Die festzulegenden Gleitkommaausnahme-Statusflags  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn alle angegebenen Ausnahmestatusflags erfolgreich festgelegt wurden, wird 0 zurückgegeben. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `fesetexceptflag` legt den Zustand der von `excepts` angegebenen Gleitkommaausnahme-Statusflags auf die Werten der entsprechenden `fexcept_t`-Objekte fest, auf die `pstatus` verweist.  Es löst die Ausnahmen aber nicht aus. Der `pstatus`-Zeiger muss auf ein gültiges `fexcept_t`-Objekt zeigen. Andernfalls ist das daraus resultierende Verhalten nicht definiert. Die Funktion `fesetexceptflag` unterstützt diese, in \<fenv.h> definierten Werte der Ausnahmemakros in `excepts`:  
  
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
|`fesetexceptflag`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetexceptflag](../../c-runtime-library/reference/fegetexceptflag2.md)
