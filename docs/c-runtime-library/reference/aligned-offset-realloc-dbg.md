---
title: _aligned_offset_realloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_realloc_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- aligned_offset_realloc_dbg
- _aligned_offset_realloc_dbg
helpviewer_keywords:
- aligned_offset_realloc_dbg function
- _aligned_offset_realloc_dbg function
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
ms.openlocfilehash: ce85fd0dec54a3963af5ae807dfb6f56f92eda7a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939766"
---
# <a name="_aligned_offset_realloc_dbg"></a>_aligned_offset_realloc_dbg

Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) belegt ist (nur in der Debugversion).

## <a name="syntax"></a>Syntax

```C
void * _aligned_offset_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Der Zeiger auf den aktuellen Speicherblock.

*size*<br/>
Die Größe der Speicherbelegung.

*alignment*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*offset*<br/>
Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den **aligned_offset_realloc** -Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der **aligned_offset_realloc** -Vorgang angefordert wurde, oder **null**.

## <a name="return-value"></a>Rückgabewert

**_aligned_offset_realloc_dbg** gibt einen void-Zeiger auf den neu belegten (und möglicherweise verschobenden) Speicherblock zurück. Der Rückgabewert ist **null** , wenn die Größe 0 (null) ist und das Puffer Argument nicht **null**ist, oder wenn nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die angegebene Größe zu erweitern. Im ersten Fall wird der ursprüngliche Block freigegeben. Im zweiten Fall wird der ursprüngliche Block nicht geändert. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

**_aligned_offset_realloc_dbg** ist eine Debugversion der [_aligned_offset_realloc](aligned-offset-realloc.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_aligned_offset_realloc_dbg** -Rückruf auf einen **_aligned_offset_realloc**-aufrufenden Wert reduziert. Sowohl **_aligned_offset_realloc** als auch **_aligned_offset_realloc_dbg** ordnen einen Speicherblock im Basisheap neu zu, **_aligned_offset_realloc_dbg** bietet jedoch mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzer Teils von der Block, der auf Verluste getestet werden soll, und *Dateiname*/, um den Ursprung von Zuordnungs Anforderungen zu bestimmen. Das Nachverfolgen spezifischer Zuordnungs Typen mit einem Blocktyp Parameter ist keine unterstützte Debugfunktion für ausgerichtete Zuordnungen. Ausgerichtete Zuordnungen werden als _NORMAL_BLOCK-Blocktyp angezeigt.

Wie [_aligned_offset_malloc](aligned-offset-malloc.md)ermöglicht **_aligned_offset_realloc_dbg** die Ausrichtung einer Struktur an einem Offset innerhalb der Struktur.

**_realloc_dbg** ordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die angeforderte *neugröße*zu. *newSize* ist möglicherweise größer oder kleiner als die Größe des ursprünglich zugeordneten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Wenn der Speicherblock verschoben wird, wird der Inhalt des ursprünglichen Blocks überschrieben.

Diese Funktion legt **errno** auf **ENOMEM** fest, wenn die Speicher Belegung fehlgeschlagen ist oder die angeforderte Größe größer als **_HEAP_MAXREQ**ist. Weitere Informationen zu **errno**finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Außerdem überprüft **_aligned_offset_realloc_dbg** seine Parameter. Wenn die *Ausrichtung* keine Potenz von 2 ist oder *Offset* größer oder gleich *Größe* und ungleich NULL ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion **null** zurück und legt **errno** auf **EINVAL**fest.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_offset_realloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
