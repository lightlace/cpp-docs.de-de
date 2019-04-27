---
title: free
ms.date: 11/04/2016
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
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: f56212874f05ea5d4ab7bd826a7a4c145551dfc0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287758"
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

*memblock*<br/>
Zuvor zugewiesener Speicherblock, der freigegeben werden soll.

## <a name="remarks"></a>Hinweise

Die **kostenlose** Funktion gibt einen Speicherblock frei (*Memblock*), die zuvor durch einen Aufruf von zugeordnet wurde **"calloc"**, **Malloc**, oder **Realloc**. Die Anzahl der freigegebenen Bytes entspricht die Anzahl der Bytes, die angefordert wurden, als der Block belegt wurde (oder im Fall von neu **Realloc**). Wenn *Memblock* ist **NULL**, der Zeiger ignoriert und **kostenlose** wird sofort zurückgegeben. Es wird versucht, einen ungültigen Zeiger freizugeben (einen Zeiger auf einen Speicherblock, der nicht zugeordnet wurde **"calloc"**, **Malloc**, oder **Realloc**) kann nachfolgende zuordnungsanforderungen beeinflussen und Fehler verursachen.

Wenn ein Fehler auftritt, bei der Freigabe von Speicher **Errno** mit Informationen aus dem Betriebssystem von der Art des Fehlers festgelegt ist. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nachdem ein Speicherblock freigegeben wurde, minimiert [_heapmin](heapmin.md) die Menge des freien Speicherplatzes auf dem Heap, indem die nicht verwendeten Bereiche zusammengefügt und wieder an das Betriebssystem freigegeben werden. Freigegebener Speicher, der nicht an das Betriebssystem freigegeben wird, wird im freien Pool wiederhergestellt und ist wieder für eine Zuordnung verfügbar.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **kostenlose** löst in [_free_dbg](free-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**Kostenlose** markiert ist `__declspec(noalias)`, was bedeutet, dass die Funktion garantiert nicht, um globale Variablen zu ändern. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).

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
