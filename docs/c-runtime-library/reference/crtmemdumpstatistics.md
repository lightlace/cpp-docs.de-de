---
title: _CrtMemDumpStatistics | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemDumpStatistics
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
apitype: DLLExport
f1_keywords:
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 59379d4916c8414717e886d6fea79e977d31836f
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics
Gibt die Debugheaderinformationen für einen angegebenen Heapzustand in einer für den Benutzer lesbaren Form aus (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `state`  
 Zeiger zum auszugebenden Heapzustand.  
  
## <a name="remarks"></a>Hinweise  
 Die `_CrtMemDumpStatistics` -Funktion gibt die Debugheaderinformationen für einen angegebenen Zustand des Heaps in einer für den Benutzer lesbaren Form aus. Die Dumpstatistik kann von der Anwendung zum Nachverfolgen von Zuordnungen und zum Erkennen von Speicherproblemen verwendet werden. Der Speicherzustands kann einen bestimmten Heapzustand oder den Unterschied zwischen zwei Zuständen enthalten. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtMemDumpStatistics` während der Vorverarbeitung entfernt.  
  
 Die `state` -Parameter muss ein Zeiger auf eine `_CrtMemState` -Struktur sein, die von [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) gefüllt oder von [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) zurückgegeben wurden, bevor `_CrtMemDumpStatistics` aufgerufen wird. Wenn `state` den Wert `NULL`annimmt, wird der ungültige Parameterhandler, wie in [Parameter Validation](../../c-runtime-library/parameter-validation.md)beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt und keine Aktion durchgeführt. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Weitere Informationen über Heapzustandsfunktionen und die `_CrtMemState`-Struktur finden Sie unter [Berichtsfunktionen für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)