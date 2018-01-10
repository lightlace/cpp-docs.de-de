---
title: feupdateenv | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: feupdateenv
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
- feupdateenv
- fenv/feupdateenv
dev_langs: C++
helpviewer_keywords: feupdateenv function
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c84e829876282a43fb9a8a17713a612e387f5216
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="feupdateenv"></a>feupdateenv
Speichert die aktuell ausgelösten Gleitkommaausnahmen, stellt den Zustand der angegebenen Gleitkommaumgebung wieder her und löst dann die gespeicherten Gleitkommaausnahmen aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
int feupdateenv(  
   const fenv_t* penv  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `penv`  
 Zeiger auf ein `fenv_t`-Objekt, das eine Gleitkommaumgebung enthält, das durch einen Aufruf von [fegetenv](fegetenv1.md) oder [feholdexcept](feholdexcept2.md) festgelegt ist. Sie können auch die standardmäßige Startgleitkommaumgebung mit dem Makro FE_DFL_ENV angeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 zurück, wenn alle Aktionen erfolgreich abgeschlossen wurden. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `feupdateenv` führt mehrere Aktionen aus. Zunächst speichert sie die aktuellen, ausgelösten Statusflags der Gleitkommaausnahmen in einem automatischen Speicher. Anschließend legt sie die aktuelle Gleitkommaumgebung aus dem im `fenv_t` Objekt gespeicherten Wert fest, auf das `penv` verweist. Wenn `penv` nicht FE_DFL_ENV ist oder nicht auf ein gültiges `fenv_t`-Objekt verweist, ist das daraus resultierende Verhalten nicht definiert. Außerdem löst `feupdateenv` die lokal gespeicherten Gleitkommaausnahmen aus.  
  
 Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`feupdateenv`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)