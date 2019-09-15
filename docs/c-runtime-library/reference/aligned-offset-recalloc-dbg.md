---
title: _aligned_offset_recalloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_recalloc_dbg
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
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
ms.openlocfilehash: e363a1cb104db9973f5f9e9c67a5d40693d405ee
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939748"
---
# <a name="_aligned_offset_recalloc_dbg"></a>_aligned_offset_recalloc_dbg

Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void * _aligned_offset_recalloc_dbg(
   void *memblock,
   size_t num,
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

*number*<br/>
Anzahl der Elemente.

*size*<br/>
Länge jedes Elements in Bytes.

*alignment*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*offset*<br/>
Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den rezuweisung-Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der rezuweisung-Vorgang angefordert wurde, oder **null**.

## <a name="return-value"></a>Rückgabewert

**_aligned_offset_recalloc_dbg** gibt einen void-Zeiger auf den neu belegten (und möglicherweise verschobenden) Speicherblock zurück. Der Rückgabewert ist **null** , wenn die Größe 0 (null) ist und das Puffer Argument nicht **null**ist, oder wenn nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die angegebene Größe zu erweitern. Im ersten Fall wird der ursprüngliche Block freigegeben. Im zweiten Fall wird der ursprüngliche Block nicht geändert. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

**_aligned_offset_realloc_dbg** ist eine Debugversion der [_aligned_offset_recalloc](aligned-offset-recalloc.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_aligned_offset_recalloc_dbg** -Rückruf auf einen **_aligned_offset_recalloc**-aufrufenden Wert reduziert. Sowohl **_aligned_offset_recalloc** als auch **_aligned_offset_recalloc_dbg** ordnen einen Speicherblock im Basisheap neu zu, **_aligned_offset_recalloc_dbg** bietet jedoch mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzer Teils. des Blocks, der auf Verluste getestet werden soll, und *Dateiname*/*LineNumber* -Informationen, um den Ursprung von Zuordnungs Anforderungen zu bestimmen. Das Nachverfolgen spezifischer Zuordnungs Typen mit einem Blocktyp Parameter ist keine unterstützte Debugfunktion für ausgerichtete Zuordnungen. Ausgerichtete Zuordnungen werden als _NORMAL_BLOCK-Blocktyp angezeigt.

**_aligned_offset_realloc_dbg** ordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die angeforderte *neugröße*zu. *newSize* ist möglicherweise größer oder kleiner als die Größe des ursprünglich zugeordneten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Wenn der Speicherblock verschoben wird, wird der Inhalt des ursprünglichen Blocks überschrieben.

Diese Funktion legt **errno** auf **ENOMEM** fest, wenn die Speicher Belegung fehlgeschlagen ist oder die angeforderte Größe (*Zahlen* * *Größe*) größer als **_HEAP_MAXREQ**ist. Weitere Informationen zu **errno**finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Außerdem überprüft **_aligned_offset_recalloc_dbg** seine Parameter. Wenn die *Ausrichtung* keine Potenz von 2 ist oder der *Offset* größer oder gleich der angeforderten Größe und ungleich 0 (null) ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion **null** zurück und legt **errno** auf **EINVAL**fest.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_offset_recalloc_dbg**|\<malloc.h>|

## <a name="see-also"></a>Siehe auch

[Datenausrichtung](../../c-runtime-library/data-alignment.md)<br/>
