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
ms.topic: article
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
caps.latest.revision: 6
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
ms.openlocfilehash: 96453fb182aa3c14bec8a296899cfcd15d39222c
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

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
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)
