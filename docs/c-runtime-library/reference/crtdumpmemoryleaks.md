---
title: _CrtDumpMemoryLeaks | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
dev_langs:
- C++
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f71e37da509d4e8dd05c5a41afa9fe539294347
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks
Legt alle Speicherblöcke im Debugheap ab, wenn ein Speicherverlust aufgetreten ist (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `_CrtDumpMemoryLeaks` gibt TRUE zurück, wenn ein Speicherverlust erkannt wird. Andernfalls gibt die Funktion FALSE zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_CrtDumpMemoryLeaks`-Funktion bestimmt, ob seit dem Beginn der Programmausführung ein Speicherverlust aufgetreten ist. Wenn ein Verlust erkannt wird, werden die Debugheaderinformationen für alle Objekte im Heap in einer für den Benutzer lesbaren Form ausgegeben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtDumpMemoryLeaks` während der Vorverarbeitung entfernt.  
  
 `_CrtDumpMemoryLeaks` wird häufig am Ende der Programmausführung aufgerufen, um zu überprüfen, ob sämtlicher Speicher, der von der Anwendung belegt wird, freigegeben wurde. Die Funktion kann bei Programmbeendigung automatisch aufgerufen werden, indem das `_CRTDBG_LEAK_CHECK_DF`-Bitfeld des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)-Flags mithilfe der [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)-Funktion aktiviert wird.  
  
 `_CrtDumpMemoryLeaks` ruft [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) auf, um den aktuellen Zustand des Heaps abzurufen, und durchsucht dann den Zustand für Speicherblöcke, die nicht freigegeben wurden. Wenn ein nicht freigegebener Block gefunden wird, ruft `_CrtDumpMemoryLeaks` die [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md)-Funktion auf, um Informationen für alle Objekte auszugeben, die seit dem Beginn der Programmausführung im Heap zugeordnet wurden.  
  
 Standardmäßig sind interne C-Laufzeitblöcke (`_CRT_BLOCK`) nicht in Speicherabbildvorgängen enthalten. Mit der [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)-Funktion kann das `_CRTDBG_CHECK_CRT_DF`-Bit von `_crtDbgFlag` aktiviert werden, um diese Blöcke bei der Erkennung von Speicherverlusten einzuschließen.  
  
 Weitere Informationen über Heapzustandsfunktionen und die `_CrtMemState` -Struktur finden Sie unter [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von `_CrtDumpMemoryLeaks` finden Sie unter [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)