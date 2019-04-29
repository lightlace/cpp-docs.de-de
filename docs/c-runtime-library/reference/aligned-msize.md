---
title: _aligned_msize
ms.date: 11/04/2016
apiname:
- _aligned_msize
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
- _aligned_msize
- aligned_msize
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
ms.openlocfilehash: 97c739eed1f54f0c6705d37542eb13c6ec6879d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341924"
---
# <a name="alignedmsize"></a>_aligned_msize

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

Die **_aligned_msize** Funktion gibt die Größe in Bytes, die durch einen Aufruf von belegten Speicherblocks zurück [_aligned_malloc](aligned-malloc.md) oder [_aligned_realloc](aligned-realloc.md). Die *Ausrichtung* und *Offset* Werte müssen identisch sein, die die Werte, die an die Funktion, die der Block belegt.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **_aligned_msize** löst in [_aligned_msize_dbg](aligned-msize-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

Diese Funktion überprüft seine Parameter. Wenn *Memblock* ist ein null-Zeiger oder *Ausrichtung* ist es sich nicht um eine Potenz von 2, **_msize** ruft der Handler für ungültige Parameter, wie in [Parametervalidierung ](../../c-runtime-library/parameter-validation.md). Die Funktion legt fest, wenn der Fehler behandelt wird, **Errno** zu **EINVAL** und gibt-1 zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
