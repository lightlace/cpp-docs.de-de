---
title: free
ms.date: 11/04/2016
api_name:
- free
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- free
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: 7e09bec7c83eae64064e3997f2e8d5632a47258a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956729"
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

Die **Free** -Funktion hebt die Zuordnung eines Speicherblocks (*memblock*) auf, der zuvor durch einen **czuzuordnungs**-, **malloc**-oder **rezuordnungsbefehl**zugeordnet wurde. Die Anzahl der freigegebenen Bytes entspricht der Anzahl der Bytes, die angefordert wurden, als der Block zugeordnet wurde (bzw. neu zugeordnet, im Fall von **rezuzuweisung**). Wenn *memblock* **null**ist, wird der Zeiger ignoriert, und **Free** wird sofort zurückgegeben. Der Versuch, einen ungültigen Zeiger freizugeben (ein Zeiger auf einen Speicherblock, der nicht von **calloc**, **malloc**oder **realloc**zugeordnet wurde), kann nachfolgende Zuordnungs Anforderungen beeinflussen und Fehler verursachen.

Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird **errno** mit Informationen aus dem Betriebssystem für die Art des Fehlers festgelegt. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Nachdem ein Speicherblock freigegeben wurde, minimiert [_heapmin](heapmin.md) die Menge des freien Speicherplatzes auf dem Heap, indem die nicht verwendeten Bereiche zusammengefügt und wieder an das Betriebssystem freigegeben werden. Freigegebener Speicher, der nicht an das Betriebssystem freigegeben wird, wird im freien Pool wiederhergestellt und ist wieder für eine Zuordnung verfügbar.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird **Free** in [_free_dbg](free-dbg.md)aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**Free** ist gekennzeichnet `__declspec(noalias)`, was bedeutet, dass die Funktion globale Variablen garantiert nicht ändert. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).

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
