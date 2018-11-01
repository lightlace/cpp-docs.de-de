---
title: _malloc_dbg
ms.date: 11/04/2016
apiname:
- _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
ms.openlocfilehash: 64fb40028d9130278077f3d05dd1e25914dba212
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633609"
---
# <a name="mallocdbg"></a>_malloc_dbg

Belegt einen Speicherblock im Heap mit zusätzlichem Speicherplatz für einen Debugheader und Überschreibungspuffern (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void *_malloc_dbg(
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Angeforderte Größe des Speicherblocks (Bytes).

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die die Belegung angefordert hat oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in denen die Belegung angefordert wurde, oder **NULL**.

Die *Filename* und *Linenumber* Parameter sind nur verfügbar, wenn **_malloc_dbg** explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)Präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreichem Abschluss diese Funktion gibt einen Zeiger an den benutzerteil des belegten Speicherblocks zurück, ruft die neue Handlerfunktion, oder gibt zurück, **NULL**. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [malloc](malloc.md)-Funktion.

## <a name="remarks"></a>Hinweise

**_malloc_dbg** ist eine Debugversion von der [Malloc](malloc.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, jeden Aufruf von **_malloc_dbg** wird nach einer Verkleinerung auf einen Aufruf von **Malloc**. Beide **Malloc** und **_malloc_dbg** belegen einen Speicherblock im Basisheap, jedoch **_malloc_dbg** bietet mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzers Teil des Blocks zum Prüfen auf Speicherverluste, einen blocktypparameter zum Nachverfolgen bestimmter belegungstypen und *Filename*/*Linenumber* -Informationen zum Ermitteln des Ursprungs von Anforderungen für speicherbelegung.

**_malloc_dbg** belegt den Speicherblock mit etwas mehr Speicherplatz als der angeforderten *Größe*. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.

**_malloc_dbg** legt **Errno** zu **ENOMEM** , wenn eine speicherbelegung fehlschlägt oder die Menge an Speicherplatz (einschließlich der bereits erwähnten Mehraufwands) überschreitet **_HEAP_ MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen über die Belegung, Initialisierung und Verwaltung der Speicherblöcke in der Debugversion des Basisheaps finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_malloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung **_malloc_dbg**, finden Sie unter [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[malloc](malloc.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
