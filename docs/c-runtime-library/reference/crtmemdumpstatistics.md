---
title: _CrtMemDumpStatistics | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.openlocfilehash: 3d5065e62248a89de8dbe0ae38f354e0ead40ba6
ms.lasthandoff: 02/24/2017

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
  
 Der `state`-Parameter muss ein Zeiger auf eine `_CrtMemState`-Struktur sein, die von [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) gefüllt oder von [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) zurückgegeben wurden, bevor `_CrtMemDumpStatistics` aufgerufen wird. Wenn `state` `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt und keine Aktion durchgeführt. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Weitere Informationen über Heapzustandsfunktionen und die `_CrtMemState`-Struktur finden Sie unter [Berichtsfunktionen für den Heapzustand](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName>  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)
