---
title: _recalloc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _recalloc
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
- _recalloc
- recalloc
dev_langs:
- C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c4ae06fbd3d10f1014fe1c879b482f30302a4f3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409302"
---
# <a name="recalloc"></a>_recalloc

Eine Kombination von **Realloc** und **Calloc**. Ordnet ein Array im Speicher neu zu und initialisiert seine Elemente auf 0.

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

*Anzahl*<br/>
Anzahl der Elemente.

*size*<br/>
Länge jedes Elements in Bytes.

## <a name="return-value"></a>Rückgabewert

**_recalloc** gibt eine **"void"** Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock.

Wenn es nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die vorgegebene Größe auszudehnen, die ursprüngliche Blockgröße ist unverändert, und **NULL** zurückgegeben wird.

Wenn die angeforderte Größe 0 (null), wird der Block verweist *Memblock* freigegeben wird; der Rückgabewert ist **NULL**, und *Memblock* bleibt bei einem freigegebenen Block verweist.

Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einem Typ außer **"void"**, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

Die **_recalloc** Funktion ändert die Größe eines belegten Blocks. Die *Memblock* Argument verweist auf den Anfang des Speicherblocks. Wenn *Memblock* ist **NULL**, **_recalloc** verhält sich genauso wie [Calloc](calloc.md) und ordnet einen neuen Block *Anzahl*  *  *Größe* Bytes. Jedes Element wird auf 0 initialisiert. Wenn *Memblock* nicht **NULL**, es muss ein Zeiger von einem vorherigen Aufruf zurückgegebene **Calloc**, ["malloc"](malloc.md), oder [Realloc ](realloc.md).

Da in einem neuen Speicherort des neuen Blocks sein kann, der zurückgegebene Zeiger durch **_recalloc** ist nicht unbedingt der Zeiger übergeben der *Memblock* Argument.

**_recalloc** legt **Errno** auf **ENOMEM** , wenn die speicherbelegung fehlschlägt oder wenn die Größe des Arbeitsspeichers größer ist als **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**Recalloc** Aufrufe **Realloc** um die c++ [_set_new_mode](set-new-mode.md) -Funktion zum Festlegen der neue handlermodus. Der neue handlermodus gibt an, ob bei einem Fehler **Realloc** ist, rufen Sie die neue Handlerroutine Isolationstransaktionen gemäß [_set_new_handler](set-new-handler.md). Standardmäßig **Realloc** auf bei einem speicherbelegungsfehler nicht die neue Handlerroutine aufgerufen. Sie können dieses Standardverhalten überschreiben, damit bei **_recalloc** Arbeitsspeicher nicht belegen kann **Realloc** die neue Handlerroutine genauso aufruft wie der **neue** Operator übernimmt, wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie

```C
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit NEWMODE.OBJ her.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **_recalloc** löst in [_recalloc_dbg](recalloc-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**_recalloc** RuntimeCompatibility `__declspec(noalias)` und `__declspec(restrict)`, was bedeutet, dass die Funktion wird sichergestellt, dass keine globalen Variablen zu ändern, und dass der zurückgegebene Zeiger nicht als Alias ist. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
