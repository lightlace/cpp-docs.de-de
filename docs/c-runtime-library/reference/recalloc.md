---
title: _recalloc
ms.date: 11/04/2016
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
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: 3bcc238dcb950a8e30af16efc557e99d933efe92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357720"
---
# <a name="recalloc"></a>_recalloc

Eine Kombination von **Realloc** und **"calloc"**. Ordnet ein Array im Speicher neu zu und initialisiert seine Elemente auf 0.

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

Wenn es nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die vorgegebene Größe auszudehnen, der ursprüngliche Block unverändert, und **NULL** zurückgegeben wird.

Wenn die angeforderte Größe 0 (null), wird der Block verweist *Memblock* wird, freigegeben; der Rückgabewert ist **NULL**, und *Memblock* bleibt verweist auf den freigegebenen Block.

Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einem Typ als **"void"**, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

Die **_recalloc** -Funktion ändert die Größe eines belegten Speicherblocks. Die *Memblock* -Argument zeigt auf den Anfang des Speicherblocks. Wenn *Memblock* ist **NULL**, **_recalloc** verhält sich genauso wie ["calloc"](calloc.md) und weist einen neuen Block an *Anzahl*  *  *Größe* Bytes. Jedes Element wird auf 0 initialisiert. Wenn *Memblock* nicht **NULL**, wird ein Zeiger von einem vorherigen Aufruf zurückgegebene **"calloc"**, [Malloc](malloc.md), oder [Realloc ](realloc.md).

Da der neue Block an einem neuen Speicherort sein kann, wird der Zeiger von zurückgegebenen **_recalloc** nicht notwendigerweise übergebenen Zeiger über die *Memblock* Argument.

**_recalloc** legt **Errno** zu **ENOMEM** , wenn die speicherbelegung fehlschlägt oder gegebenenfalls die Größe des Arbeitsspeichers übersteigt **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**Recalloc** Aufrufe **Realloc** um verwenden die C++ [_set_new_mode](set-new-mode.md) Funktion, um den neuen handlermodus festzulegen. Der neue handlermodus gibt an, ob bei einem Fehler **Realloc** besteht darin, rufen Sie die neue Handlerroutine mit [_set_new_handler](set-new-handler.md). In der Standardeinstellung **Realloc** Ruft die neue Handlerroutine nicht bei einem Fehler, um Speicher zu belegen. Sie können dieses Standardverhalten überschreiben, damit, wenn **_recalloc** ein Fehler auftritt, bei der speicherbelegung **Realloc** die neue Handlerroutine aufruft, in der gleichen Weise wie die **neue** Operator führt, wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie

```C
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit NEWMODE.OBJ her.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **_recalloc** löst in [_recalloc_dbg](recalloc-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**_recalloc** RuntimeCompatibility `__declspec(noalias)` und `__declspec(restrict)`, was bedeutet, dass die Funktion nicht, so ändern Sie globale Variablen definitiv, und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

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
