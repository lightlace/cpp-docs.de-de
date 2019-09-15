---
title: _malloc_dbg
ms.date: 11/04/2016
api_name:
- _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
ms.openlocfilehash: cfaaaec17dc8546c937045f93027e9609981bd93
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952881"
---
# <a name="_malloc_dbg"></a>_malloc_dbg

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
Zeiger auf den Namen der Quelldatei, die den Zuordnungs Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der Zuordnungs Vorgang angefordert wurde, oder **null**.

Die Parameter " *filename* " und " *LineNumber* " sind nur verfügbar, wenn " **_malloc_dbg** " explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) -präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Nach erfolgreichem Abschluss gibt diese Funktion einen Zeiger auf den Benutzer Teil des belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt **null**zurück. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [malloc](malloc.md)-Funktion.

## <a name="remarks"></a>Hinweise

**_malloc_dbg** ist eine Debugversion der [malloc](malloc.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_malloc_dbg** -Rückruf auf einen **malloc**-Aufrufwert reduziert. Sowohl **malloc** als auch **_malloc_dbg** weisen einen Speicherblock im Basisheap zu, aber **_malloc_dbg** bietet mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzer Teils des Blocks zum Prüfen auf Speicher Verluste, einen Blocktyp Parameter zum Nachverfolgen bestimmte Zuordnungs Typen und *Dateiname*/-*LineNumber* -Informationen, um den Ursprung von Zuordnungs Anforderungen zu bestimmen.

**_malloc_dbg** ordnet den Speicherblock mit etwas mehr Speicherplatz als die angeforderte *Größe*zu. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.

**_malloc_dbg** legt **errno** auf **ENOMEM** fest, wenn eine Speicher Belegung fehlschlägt oder wenn der benötigte Speicherplatz (einschließlich des bereits erwähnten Mehraufwands) **_HEAP_MAXREQ**überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen über die Belegung, Initialisierung und Verwaltung der Speicherblöcke in der Debugversion des Basisheaps finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_malloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **_malloc_dbg**finden Sie unter [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[malloc](malloc.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
