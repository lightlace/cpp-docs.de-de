---
title: _aligned_recalloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_recalloc_dbg
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
- _aligned_recalloc_dbg
- aligned_recalloc_dbg
helpviewer_keywords:
- aligned_recalloc_dbg function
- _aligned_recalloc_dbg function
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
ms.openlocfilehash: 85af821aaa873b6e71341823d47085996f697235
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664697"
---
# <a name="alignedrecallocdbg"></a>_aligned_recalloc_dbg

Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void * _aligned_recalloc_dbg(
   void * memblock,
   size_t num,
   size_t size,
   size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Der Zeiger auf den aktuellen Speicherblock.

*Anzahl*<br/>
Die Anzahl der Elemente.

*size*<br/>
Die Größe jedes Elements in Byte.

*Ausrichtung*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die Belegung angefordert oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in denen Belegung angefordert wurde, oder **NULL**.

## <a name="return-value"></a>Rückgabewert

**_aligned_realloc_dbg** gibt einen void-Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock zurück. Der Rückgabewert ist **NULL** Wenn die Größe 0 (null beträgt) und das pufferargument nicht **NULL**, oder wenn nicht genügend Arbeitsspeicher verfügbar, um den Block auf die vorgegebene Größe auszudehnen. Im ersten Fall wird der ursprüngliche Block freigegeben. Im zweiten Fall wird der ursprüngliche Block nicht geändert. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.

Es ist ein Fehler, wenn ein Speicher neu belegt und die Ausrichtung eines Blocks geändert wird.

## <a name="remarks"></a>Hinweise

**_aligned_realloc_dbg** ist eine Debugversion von der [_aligned_recalloc](aligned-recalloc.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, jeden Aufruf von **_aligned_recalloc_dbg** wird nach einer Verkleinerung auf einen Aufruf von **_aligned_recalloc**. Beide **_aligned_recalloc** und **_aligned_recalloc_dbg** belegen einen Speicherblock im Basisheap, neu, aber **_aligned_recalloc_dbg** unterstützt mehrere Debuggen Funktionen: Puffer auf beiden Seiten des benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen blocktypparameter zum Nachverfolgen bestimmter belegungstypen und *Filename*/*Linenumber* Informationen zum Ermitteln des Ursprungs von belegungsanforderungen.

**_aligned_realloc_dbg** zuordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die angeforderte Größe (*Anzahl* * *Größe*) kann der größer oder kleiner sein als die Größe des ursprünglich zugeordneten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Der Benutzerteil des Blocks wird mit dem Wert 0xCD gefüllt, und die Überschreibungspuffer werden mit 0xFD gefüllt.

**_aligned_realloc_dbg** legt **Errno** zu **ENOMEM** , wenn eine speicherbelegung fehlschlägt. **EINVAL** wird zurückgegeben, wenn der Umfang des erforderlichen Arbeitsspeichers (einschließlich der bereits erwähnten Mehraufwands) überschreitet **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Darüber hinaus **_aligned_recalloc_dbg** überprüft die eigenen Parameter. Wenn *Ausrichtung* ist es sich nicht um eine Potenz von 2 ist, ruft diese Funktion den Handler für ungültige Parameter wie beschrieben in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **NULL** und **Errno** zu **EINVAL**.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_recalloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
