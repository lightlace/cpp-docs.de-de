---
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 96fe9e7fda0d0cdfdbfa5462e4f601e3649e2233
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348873"
---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg

Belegt Speicher in einer angegebenen Ausrichtungsgrenze (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void * _aligned_offset_malloc_dbg(
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Die Größe der angeforderten Speicherbelegung.

*alignment*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*offset*<br/>
Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die die Belegung angefordert hat oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in denen die Belegung angefordert wurde, oder **NULL**.

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Speicherblock, der zugewiesen wurde oder **NULL** bei fehlgeschlagenem Vorgang.

## <a name="remarks"></a>Hinweise

**_aligned_offset_malloc_dbg** ist eine Debugversion von der [_aligned_offset_malloc](aligned-offset-malloc.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, jeden Aufruf von **_aligned_offset_malloc_dbg** wird nach einer Verkleinerung auf einen Aufruf von **_aligned_offset_malloc**. Beide **_aligned_offset_malloc** und **_aligned_offset_malloc_dbg** belegen einen Speicherblock im Basisheap, jedoch **_aligned_offset_malloc_dbg** verfügt über mehrere Debugfunktionen: Puffer auf beiden Seiten des benutzerteils des Blocks zum Prüfen auf Speicherverluste, und *Filename*/*Linenumber* -Informationen zum Ermitteln des Ursprungs von Anforderungen für speicherbelegung. Nachverfolgen von bestimmten belegungstypen mit einem blocktypparameter ist kein unterstützten Debug-Feature für ausgerichtete Zuweisungen. Ausgerichtete Zuweisungen werden als ein _NORMAL_BLOCK-Block-Typ angezeigt.

**_aligned_offset_malloc_dbg** belegt den Speicherblock mit etwas mehr Speicherplatz als der angeforderten *Größe*. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.

**_aligned_offset_malloc_dbg** eignet sich für Situationen, in denen Ausrichtung für ein geschachteltes Element; erforderlich ist z. B., wenn die Ausrichtung auf eine geschachtelte Klasse erforderlich war.

**_aligned_offset_malloc_dbg** basiert auf **Malloc**; Weitere Informationen finden Sie unter [Malloc](malloc.md).

Diese Funktion legt **Errno** zu **ENOMEM** , wenn die speicherbelegung fehlgeschlagen ist oder die angeforderte Größe größer als war **_HEAP_MAXREQ**. Weitere Informationen zu **Errno**, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus **_aligned_offset_malloc** überprüft die eigenen Parameter. Wenn *Ausrichtung* ist keine Potenz von 2 ist oder wenn *Offset* ist größer als oder gleich *Größe* und ungleich NULL ist, ruft diese Funktion den Handler für ungültige Parameter wie beschrieben in [ Parametervalidierung](../../c-runtime-library/parameter-validation.md). Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **NULL** und **Errno** zu **EINVAL**.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
