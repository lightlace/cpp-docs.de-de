---
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 4fbacb170fd1ae1ce92de4a11ea85ff42b3942a0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939773"
---
# <a name="_aligned_offset_malloc_dbg"></a>_aligned_offset_malloc_dbg

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
Zeiger auf den Namen der Quelldatei, die den Zuordnungs Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der Zuordnungs Vorgang angefordert wurde, oder **null**.

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Speicherblock, der zugeordnet wurde, oder **null** , wenn der Vorgang fehlgeschlagen ist.

## <a name="remarks"></a>Hinweise

**_aligned_offset_malloc_dbg** ist eine Debugversion der [_aligned_offset_malloc](aligned-offset-malloc.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_aligned_offset_malloc_dbg** -Rückruf auf einen **_aligned_offset_malloc**-aufrufenden Wert reduziert. Sowohl **_aligned_offset_malloc** als auch **_aligned_offset_malloc_dbg** weisen einen Speicherblock im Basisheap zu, **_aligned_offset_malloc_dbg** bietet jedoch mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzer Teils des Blocks für Testen Sie auf Lecks und *Dateiname*/, um den Ursprung von Zuordnungs Anforderungen zu bestimmen. Das Nachverfolgen spezifischer Zuordnungs Typen mit einem Blocktyp Parameter ist keine unterstützte Debugfunktion für ausgerichtete Zuordnungen. Ausgerichtete Zuordnungen werden als _NORMAL_BLOCK-Blocktyp angezeigt.

**_aligned_offset_malloc_dbg** ordnet den Speicherblock mit etwas mehr Speicherplatz als die angeforderte *Größe*zu. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.

**_aligned_offset_malloc_dbg** ist in Situationen nützlich, in denen eine Ausrichtung für ein struktursted Element erforderlich ist. beispielsweise, wenn die Ausrichtung für eine in einer Klasse eine Klasse erforderlich war.

**_aligned_offset_malloc_dbg** basiert auf **malloc**; Weitere Informationen finden Sie unter [malloc](malloc.md).

Diese Funktion legt **errno** auf **ENOMEM** fest, wenn die Speicher Belegung fehlgeschlagen ist oder die angeforderte Größe größer als **_HEAP_MAXREQ**ist. Weitere Informationen zu **errno**finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Außerdem überprüft **_aligned_offset_malloc** seine Parameter. Wenn die *Ausrichtung* keine Potenz von 2 ist oder *Offset* größer oder gleich *Größe* und ungleich NULL ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion **null** zurück und legt **errno** auf **EINVAL**fest.

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
