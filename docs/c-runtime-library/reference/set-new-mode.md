---
title: _set_new_mode | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_new_mode
- _set_new_mode
dev_langs:
- C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 57a578f8accf7244d71c0d8791a6e898ead7d242
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="setnewmode"></a>_set_new_mode
Legt einen neuen Handlermodus für `malloc` fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `newhandlermode`  
 Neuer Handlermodus für `malloc`; gültiger Wert ist 0 oder 1.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den vorherigen Handlermodus zurück, der für `malloc` festgelegt wurde. Ein Rückgabewert 1 gibt an, dass `malloc` bei einem Speicherbelegungsproblem zuvor die neue Handlerroutine aufruft. Ein Rückgabewert 0 gibt an, dass dies nicht der Fall ist. Wenn die `newhandlermode` Argument stimmt nicht mit 0 oder 1, wird-1 zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die C++-Funktion `_set_new_mode` legt den neuen Handlermodus für [malloc](../../c-runtime-library/reference/malloc.md) fest. Der neue Handlermodus gibt an, ob bei einem Fehler `malloc` die neue Handlerroutine aufrufen soll, wie dies von [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist. Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf. Sie können dieses Standardverhalten überschreiben, sodass, wenn `malloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`-Operator, wenn dieser aus demselben Grund fehlschlägt. Weitere Informationen finden Sie unter den Operatoren [new](../../cpp/new-operator-cpp.md) und [delete](../../cpp/delete-operator-cpp.md) in der *C++-Sprachreferenz*. Um den Standardwert zu überschreiben, rufen Sie  
  
```  
_set_new_mode(1)  
```  
  
 rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit Newmode.obj (siehe [Link Options (Linkoptionen)](../../c-runtime-library/link-options.md)) her.  
  
 Diese Funktion überprüft seine Parameter. Wenn `newhandlermode` ungleich 0 oder 1 ist, ruft die Funktion, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben, den Handler für ungültige Parameter auf. Wenn die weitere Ausführung zugelassen wird, gibt **_**`set_new_mode` -1 zurück und setzt `errno` auf `EINVAL`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_set_new_mode`|\<new.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [_query_new_mode](../../c-runtime-library/reference/query-new-mode.md)
