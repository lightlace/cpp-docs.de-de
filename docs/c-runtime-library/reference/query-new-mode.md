---
title: _query_new_mode | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _query_new_mode
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
- query_new_mode
- _query_new_mode
dev_langs:
- C++
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 38b5022412f3f07806fcb7a2cea373457c8b405f
ms.lasthandoff: 02/24/2017

---
# <a name="querynewmode"></a>_query_new_mode
Gibt eine Ganzzahl zurück, die den von `_set_new_mode` für `malloc` festgelegten neuen Handlermodus anzeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen neuen Handlermodus zurück, nämlich 0 oder 1 für `malloc`. Ein Rückgabewert 1 gibt an, dass `malloc` bei einem Speicherbelegungsproblem die neue Handlerroutine aufruft. Ein Rückgabewert 0 gibt an, dass dies nicht der Fall ist.  
  
## <a name="remarks"></a>Hinweise  
 Die C++-Funktion `_query_new_mode` gibt eine ganze Zahl zurück, die den neuen Handlermodus angibt, der von der C++-Funktion [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) für [malloc](../../c-runtime-library/reference/malloc.md) festgelegt wird. Der neue Handlermodus gibt an, ob `malloc` bei einem Fehler bei der Speicherbelegung die neue Handlerroutine aufrufen soll, wie dies von [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist. Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler die neue Handlerroutine nicht auf. Sie können dieses Standardverhalten mit `_set_new_mode` überschreiben, damit `malloc` bei einem Fehler die neue Handlerroutine genauso aufruft wie der **new**-Operator, wenn dieser aus demselben Grund fehlschlägt. Weitere Informationen finden Sie unter der Erläuterung [new and delete operators (Operatoren new und delete)](../../cpp/new-and-delete-operators.md) in der C++-Sprachreferenz.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_query_new_mode`|\<new.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)
