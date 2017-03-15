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
apiname:
- feholdexcept
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
dev_langs:
- C++
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: 5
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 40c56f3ebd01ac809b48c48dcda85ef8a3217be4
ms.lasthandoff: 02/24/2017

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
 Gibt null zurück, allerdings nur, wenn die Funktion erfolgreich die ununterbrochene Behandlung von Gleitkommaausnahmen aktivieren kann.  
  
## <a name="remarks"></a>Hinweise  
 Die `feholdexcept`-Funktion wird verwendet, um den Status der aktuellen Gleitkommaumgebung in das `fenv_t`-Objekt zu speichern, auf das von `penv` gezeigt wird, und um einzustellen, dass die Ausführung von Gleitkommaausnahmen nicht von der Umgebung unterbrochen wird. Dies wird als ununterbrochener Modus bezeichnet.  Dieser Modus wird fortgesetzt, bis die Umgebung mithilfe von [fesetenv](http://msdn.microsoft.com/Library/a34b2705-0bd4-452e-a30f-eea3898d8183) oder [feupdateenv](../../c-runtime-library/reference/feupdateenv.md) wiederhergestellt wird.  
  
 Sie können diese Funktion am Anfang einer Unterroutine verwenden, die eine oder mehrere Gleitkommaausnahmen vor dem Aufrufer verbergen muss. Um eine Ausnahme zu melden, löschen Sie einfach die unerwünschten Ausnahmen mithilfe von [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md), und beenden Sie dann den ununterbrochenen Modus durch Aufruf von `feupdateenv`.  
  
 Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|C-Header|C++-Header|  
|--------------|--------------|------------------|  
|`feholdexcept`|\<fenv.h>|\<cfenv>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](http://msdn.microsoft.com/Library/a34b2705-0bd4-452e-a30f-eea3898d8183)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)
