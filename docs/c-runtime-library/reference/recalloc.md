---
title: _recalloc
ms.date: 11/04/2016
api_name:
- _recalloc
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
- _recalloc
- recalloc
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: f06631fe4dd0abcb0b18895ccb04e5b52cda6a2c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949449"
---
# <a name="_recalloc"></a>_recalloc

Eine Kombination aus **rezuweisung** und **czuweisung**. Ordnet ein Array im Speicher neu zu und initialisiert seine Elemente auf 0.

## <a name="syntax"></a>Syntax

```C
void *_recalloc(
   void *memblock
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Zeiger zum vorherigen belegten Speicherblock.

*number*<br/>
Anzahl der Elemente.

*size*<br/>
Länge jedes Elements in Bytes.

## <a name="return-value"></a>Rückgabewert

**_recalloc** gibt einen **void** -Zeiger auf den neu belegten (und möglicherweise verschobenden) Speicherblock zurück.

Wenn nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die angegebene Größe auszudehnen, bleibt der ursprüngliche Block unverändert, und **null** wird zurückgegeben.

Wenn die angeforderte Größe 0 (null) ist, wird der Block, auf den *memblock* zeigt, freigegeben. der Rückgabewert ist **null**, und *memblock* zeigt auf einen freigegebenen Block.

Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als **void**abzurufen, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

Die **_recalloc** -Funktion ändert die Größe eines zugeordneten Speicherblocks. Das *memblock* -Argument zeigt auf den Anfang des Speicherblocks. Wenn *memblock* den Wert **null**hat, verhält sich **_recalloc** genauso [wie czuzuordnen](calloc.md) und ordnet einen neuen Block von *Zahlen* * *Größe* in Bytes zu. Jedes Element wird auf 0 initialisiert. Wenn *memblock* nicht **null**ist, sollte es sich um einen Zeiger handeln, der von einem vorherigen **czuzuordnungsbefehl**, [malloc](malloc.md)oder [rezuweisung](realloc.md)zurückgegeben wurde.

Da sich der neue-Block an einem neuen Speicherort befinden kann, ist der Zeiger, der von **_recalloc** zurückgegeben wird, nicht garantiert der Zeiger, der durch das *memblock* -Argument durchlaufen wird.

**_recalloc** legt **errno** auf " **endomem** " fest, wenn die Speicher Belegung fehlschlägt oder wenn der angeforderte Arbeitsspeicher den Wert von **_HEAP_MAXREQ**überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**recbelegc** ruft **rezuzuordnungen** auf, um die C++ [_set_new_mode](set-new-mode.md) -Funktion zum Festlegen des neuen handlermodus zu verwenden. Der neue handlermodus gibt an, ob bei einem Fehler **rezuzuweisung** die neue Handlerroutine aufrufen soll, wie von [_set_new_handler](set-new-handler.md)festgelegt. Standardmäßig ruft **realloc** bei einem Fehler bei der Speicherzuweisung nicht die neue Handlerroutine auf. Sie können dieses Standardverhalten überschreiben, sodass, wenn **_recalloc** keinen Arbeitsspeicher zuordnen kann, die neue Handlerroutine von **realloc** auf dieselbe Weise aufgerufen wird, die der **neue** Operator bei einem Fehler aus demselben Grund verwendet. Um den Standardwert zu überschreiben, rufen Sie

```C
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit NEWMODE.OBJ her.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird **_recalloc** in [_recalloc_dbg](recalloc-dbg.md)aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**_recalloc** ist als `__declspec(noalias)` und `__declspec(restrict)`gekennzeichnet. Dies bedeutet, dass die Funktion globale Variablen garantiert nicht ändert und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> und \<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[free](free.md)<br/>
[Linkoptionen](../../c-runtime-library/link-options.md)<br/>
