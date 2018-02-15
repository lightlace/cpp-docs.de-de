---
title: Fesetenv | Microsoft Docs
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
- fesetenv
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
- fesetenv
- fenv/fesetenv
dev_langs:
- C++
helpviewer_keywords:
- fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2717c0fee2582cac3c9013f3f49ff37744cbde9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="fesetenv"></a>fesetenv
Legt die aktuelle Gleitkommaausnahme fest  
  
## <a name="syntax"></a>Syntax  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `penv`  
 Zeiger auf ein `fenv_t`-Objekt, das eine Gleitkommaumgebung enthält, das durch einen Aufruf von [fegetenv](fegetenv1.md) oder [feholdexcept](feholdexcept2.md) festgelegt ist. Sie können auch die standardmäßige Startgleitkommaumgebung mit dem Makro FE_DFL_ENV angeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 zurück, wenn die Umgebung erfolgreich eingerichtet wurde. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `fesetenv` legt die aktuelle Gleitkommaumgebung aus dem im `fenv_t`-Objekt gespeicherten Wert fest, auf das `penv` verweist. Die Gleitkommaumgebung ist ein Satz von Statusflags und Steuermodi, die Gleitkommaberechnungen beeinflussen. Dies beinhaltet das Rundungsverhalten und die Statusflags für Gleitkommaausnahmen.  Wenn `penv` nicht FE_DFL_ENV ist oder nicht auf ein gültiges `fenv_t`-Objekt verweist, ist das daraus resultierende Verhalten nicht definiert.  
  
 Ein Aufruf dieser Funktion legt die Ausnahmestatusflags im `penv`-Objekt fest, löst diese Ausnahmen aber nicht aus.  
  
 Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`fesetenv`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)