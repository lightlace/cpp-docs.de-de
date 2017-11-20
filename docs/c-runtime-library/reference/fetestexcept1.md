---
title: fetestexcept1 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: fetestexcept
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
- fetestexcept
- fenv/fetestexcept
dev_langs: C++
helpviewer_keywords: fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a2fa4448bc71fc8b01abffaa0655f63e6ef474a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="fetestexcept"></a>fetestexcept
Bestimmt, welche der angegebenen Gleitkommaausnahme-Statusflags momentan festgelegt sind  
  
## <a name="syntax"></a>Syntax  
  
```  
int fetestexcept(  
   int excepts  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `excepts`  
 Bitweiser OR der zu testenden Gleitkomma-Statusflags  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg eine Bitmaske mit einem bitweisen OR der Gleitkommaausnahme-Makros zurück, die den derzeit festgelegten Ausnahmestatusflags entsprechen. Gibt 0 zurück, wenn keine Ausnahmen festgelegt wurden.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die Funktion „fetestexcept“, um zu bestimmen, welche Ausnahmen durch einen Gleitkommavorgang ausgelöst wurden. Verwenden Sie den Parameter `excepts`, um die zu testenden Ausnahmestatusflags anzugeben. Die Funktion `fetestexcept` verwendet diese in \<fenv.h> definierten Ausnahmemakros in `excepts` und den Rückgabewert:  
  
|Ausnahmemakro|Beschreibung|  
|---------------------|-----------------|  
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|  
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|  
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|  
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|  
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|  
|FE_ALLEXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|  
  
 Das angegebene Argument `excepts` kann entweder 0, eines der unterstützten Gleitkommaausnahme-Makros oder das bitweise OR von mindestens zwei der Makros sein. Der Effekt von jedem anderen `excepts`-Argumentwert ist nicht definiert.  
  
 Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`fetestexcept`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feraiseexcept](../../c-runtime-library/reference/feraiseexcept.md)