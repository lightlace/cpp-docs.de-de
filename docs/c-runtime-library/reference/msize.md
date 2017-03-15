---
title: _msize | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _msize
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
- msize
- _msize
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: 12
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
ms.openlocfilehash: 9bc43a31b7e65bfd6ccb5aef83e7fbf7c76edaaf
ms.lasthandoff: 02/24/2017

---
# <a name="msize"></a>_msize
Gibt die Größe eines im Heap belegten Speicherblocks zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Zeiger zum Speicherblock.  
  
## <a name="return-value"></a>Rückgabewert  
 `_msize` gibt die Größe (in Bytes) als ganze Zahl ohne Vorzeichen zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_msize`-Funktion gibt die Größe des Speicherblocks (in Bytes) zurück, der durch einen Aufruf von `calloc`, `malloc` oder `realloc` belegt wurde.  
  
 Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird `_msize` in [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md) aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [The CTR Debug Heap (CRT-Debugheap)](/visualstudio/debugger/crt-debug-heap-details).  
  
 Diese Funktion überprüft seine Parameter. Wenn `memblock` ein NULL-Zeiger ist, ruft `_msize` wie unter [Parameter Validation (Parametervalidierung)](../../c-runtime-library/parameter-validation.md) beschrieben einen Handler für ungültige Parameter auf. Wenn der Fehler behandelt wird, legt die Funktion `errno` auf `EINVAL` fest und gibt -1 zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie unter [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_expand](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)
