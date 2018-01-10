---
title: feholdexcept2 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: feholdexcept
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
- feholdexcept
- fenv/feholdexcept
dev_langs: C++
helpviewer_keywords: feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1455f3b963c2d9faf7c2e96a2d6684e0e412ef8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="feholdexcept"></a>feholdexcept
Speichert die aktuelle Gleitkommaumgebung im angegebenen Objekt, löscht die Gleitkomma-Statusflags und setzt die Gleitkommaumgebung wenn möglich in den ununterbrochenen Modus.  
  
## <a name="syntax"></a>Syntax  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `penv`  
 Zeiger auf ein `fenv_t`-Objekt, der eine Kopie der Gleitkommaumgebung enthalten soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null) zurück, wenn die Funktion erfolgreich unterbrechungsfreier Gleitkommaausnahmen behandeln aktivieren kann.  
  
## <a name="remarks"></a>Hinweise  
 Die `feholdexcept`-Funktion wird verwendet, um den Status der aktuellen Gleitkommaumgebung in das `fenv_t`-Objekt zu speichern, auf das von `penv` gezeigt wird, und um einzustellen, dass die Ausführung von Gleitkommaausnahmen nicht von der Umgebung unterbrochen wird. Dies wird als ununterbrochener Modus bezeichnet.  Dieser Modus wird fortgesetzt, bis die Umgebung mithilfe von [fesetenv](fesetenv1.md) oder [feupdateenv](../../c-runtime-library/reference/feupdateenv.md) wiederhergestellt wird.  
  
 Sie können diese Funktion am Anfang einer Unterroutine verwenden, die eine oder mehrere Gleitkommaausnahmen vor dem Aufrufer verbergen muss. Um eine Ausnahme zu melden, löschen Sie einfach die unerwünschten Ausnahmen mithilfe von [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md), und beenden Sie dann den ununterbrochenen Modus durch Aufruf von `feupdateenv`.  
  
 Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`feholdexcept`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](fesetenv1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)