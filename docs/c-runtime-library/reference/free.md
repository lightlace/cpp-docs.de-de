---
title: free | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- free
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
- free
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc6dfd832d18dbabc1ebc10aec252cc8afe15346
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402516"
---
# <a name="free"></a>free

Hebt die Zuweisung eines Speicherblocks auf oder gibt diesen frei.

## <a name="syntax"></a>Syntax

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>Parameter

*Memblock* zuvor reservierten Speicherblock freigegeben wird.

## <a name="remarks"></a>Hinweise

Die **freien** Funktion hebt die Zuordnung eines Speicherblocks (*Memblock*), die zuvor durch einen Aufruf von belegt wurde **Calloc**, **"malloc"**, oder **Realloc**. Die Anzahl der freigegebenen Bytes entspricht die Anzahl der Bytes, die angefordert werden, wenn der Block belegt wurde (oder im Fall des neu belegten **Realloc**). Wenn *Memblock* ist **NULL**, der Zeiger wird ignoriert und **freien** wird sofort zurückgegeben. Bei dem Versuch, einen ungültigen Zeiger frei (ein Zeiger auf einen Speicherblock, der nicht durch belegt wurde **Calloc**, **"malloc"**, oder **Realloc**) wirken sich auf nachfolgende belegungsanforderungen und Fehler verursachen.

Wenn ein Fehler auftritt, bei der Freigabe des Arbeitsspeichers und **Errno** mit Informationen des Betriebssystems über die Art des Fehlers festgelegt ist. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nachdem ein Speicherblock freigegeben wurde, minimiert [_heapmin](heapmin.md) die Menge des freien Speicherplatzes auf dem Heap, indem die nicht verwendeten Bereiche zusammengefügt und wieder an das Betriebssystem freigegeben werden. Freigegebener Speicher, der nicht an das Betriebssystem freigegeben wird, wird im freien Pool wiederhergestellt und ist wieder für eine Zuordnung verfügbar.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **freien** löst in [_free_dbg](free-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**freier** RuntimeCompatibility `__declspec(noalias)`, was bedeutet, dass die Funktion gewährleistet ist, nicht um die globalen Variablen zu ändern. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).

Um Speicher mit [_malloca](malloca.md) freizugeben, verwenden Sie [_freea](freea.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**free**|\<stdlib.h> und \<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [malloc](malloc.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
