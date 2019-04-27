---
title: _msize_dbg
ms.date: 11/04/2016
apiname:
- _msize_dbg
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
- _msize_dbg
- msize_dbg
helpviewer_keywords:
- memory blocks
- _msize_dbg function
- msize_dbg function
ms.assetid: a333f4b6-f8a2-4e61-bb69-cb34063b8cef
ms.openlocfilehash: 3b6d08d44162d8263ca88147fe86166924d7d162
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156303"
---
# <a name="msizedbg"></a>_msize_dbg

Berechnet die Größe eines Speicherblocks im Heap (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
size_t _msize_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>Parameter

*userData*<br/>
Zeiger zu dem Speicherblock, für den die Größen bestimmt werden soll.

*blockType*<br/>
Typ des angegebenen Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreichem Abschluss **_msize_dbg** gibt die Größe (in Bytes) des angegebenen Speicherblocks; andernfalls **NULL**.

## <a name="remarks"></a>Hinweise

**_msize_dbg** ist eine Debugversion der _[Msize](msize.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, jeden Aufruf von **_msize_dbg** wird nach einer Verkleinerung auf einen Aufruf von **_msize**. Beide **_msize** und **_msize_dbg** berechnen Sie die Größe eines Speicherblocks im Basisheap, jedoch **_msize_dbg** fügt zwei Debugfunktionen: Es schließt die Puffer auf beiden Seiten des benutzerteils des Speicherblocks, in der zurückgegebenen Größe ein, und ermöglicht größenberechnungen für bestimmte Blocktypen.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild finden Sie unter [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Diese Funktion überprüft seine Parameter. Wenn *Memblock* ist ein null-Zeiger **_msize** ruft der Handler für ungültige Parameter, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Die Funktion legt fest, wenn der Fehler behandelt wird, **Errno** zu **EINVAL** und gibt-1 zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_msize_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_msize_dbg.c
// compile with: /MTd
/*
* This program allocates a block of memory using _malloc_dbg
* and then calls _msize_dbg to display the size of that block.
* Next, it uses _realloc_dbg to expand the amount of
* memory used by the buffer and then calls _msize_dbg again to
* display the new amount of memory allocated to the buffer.
*/

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
        long *buffer, *newbuffer;
        size_t size;

        /*
         * Call _malloc_dbg to include the filename and line number
         * of our allocation request in the header
         */
        buffer = (long *)_malloc_dbg( 40 * sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );
        if( buffer == NULL )
               exit( 1 );

        /*
         * Get the size of the buffer by calling _msize_dbg
         */
        size = _msize_dbg( buffer, _NORMAL_BLOCK );
        printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

        /*
         * Reallocate the buffer using _realloc_dbg and show the new size
         */
        newbuffer = _realloc_dbg( buffer, size + (40 * sizeof(long)), _NORMAL_BLOCK, __FILE__, __LINE__ );
        if( newbuffer == NULL )
               exit( 1 );
        buffer = newbuffer;
        size = _msize_dbg( buffer, _NORMAL_BLOCK );
        printf( "Size of block after _realloc_dbg of 40 more longs: %u\n", size );

        free( buffer );
        exit( 0 );
}
```

### <a name="output"></a>Output

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _realloc_dbg of 40 more longs: 320
```

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
