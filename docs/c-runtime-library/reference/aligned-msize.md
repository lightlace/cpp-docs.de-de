---
title: _aligned_msize
ms.date: 11/04/2016
api_name:
- _aligned_msize
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
- _aligned_msize
- aligned_msize
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
ms.openlocfilehash: 922224dc81858076770a36551df26c89940b3282
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943906"
---
# <a name="_aligned_msize"></a>_aligned_msize

Gibt die Größe eines im Heap belegten Speicherblocks zurück.

## <a name="syntax"></a>Syntax

```C
size_t _msize(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Zeiger zum Speicherblock.

*alignment*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*offset*<br/>
Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.

## <a name="return-value"></a>Rückgabewert

Gibt die Größe (in Bytes) als ganze Zahl ohne Vorzeichen zurück.

## <a name="remarks"></a>Hinweise

Die **_aligned_msize** -Funktion gibt die Größe des Speicherblocks (in Bytes) zurück, der durch einen-Befehl von [_aligned_malloc](aligned-malloc.md) oder [_aligned_realloc](aligned-realloc.md)zugeordnet wird. Die *Ausrichtungs* -und *Offset* Werte müssen mit den Werten identisch sein, die an die Funktion, die den Block zugeordnet hat, übermittelt wurden.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird **_aligned_msize** in [_aligned_msize_dbg](aligned-msize-dbg.md)aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

Diese Funktion überprüft seine Parameter. Wenn *memblock* ein NULL-Zeiger ist oder die *Ausrichtung* keine Potenz von 2 ist, ruft **_msize** einen Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn der Fehler behandelt wird, legt die Funktion **errno** auf **EINVAL** fest und gibt-1 zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
