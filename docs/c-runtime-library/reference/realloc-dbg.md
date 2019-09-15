---
title: _realloc_dbg
ms.date: 11/04/2016
api_name:
- _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
ms.openlocfilehash: 58d12ed6f4b013996f3f59cba1b146b823adbee6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949510"
---
# <a name="_realloc_dbg"></a>_realloc_dbg

Belegt einen angegebenen Speicherblock im Heap durch Verschieben und/oder Ändern der Größe des Blocks erneut (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void *_realloc_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*userData*<br/>
Zeiger zum vorherigen belegten Speicherblock.

*newSize*<br/>
Angeforderte Größe für den neu belegten Block (Bytes).

*blockType*<br/>
Angeforderter Typ für den neu zugeordneten Block: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den **rezuweisung** -Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der **rezuweisung** -Vorgang angefordert wurde, oder **null**.

Die Parameter " *filename* " und " *LineNumber* " sind nur verfügbar, wenn " **_realloc_dbg** " explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) -präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Nach erfolgreichem Abschluss gibt diese Funktion entweder einen Zeiger auf den Benutzer Teil des neu belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt **null**zurück. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der Funktion [realloc](realloc.md).

## <a name="remarks"></a>Hinweise

**_realloc_dbg** ist eine Debugversion der [rezuweisung](realloc.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_realloc_dbg** -Rückruf auf einen **rezuweisung**-Rückruf reduziert. Sowohl **realloc** als auch **_realloc_dbg** ordnen einen Speicherblock im Basisheap neu zu, aber **_realloc_dbg** verfügt über mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzer Teils des Blocks zum Prüfen auf Speicher Verluste, einen Blocktyp Parameter für Überprüfen Sie bestimmte Zuordnungs Typen und *Dateiname*/*LineNumber* -Informationen, um den Ursprung von Zuordnungs Anforderungen zu bestimmen.

**_realloc_dbg** ordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die angeforderte *neugröße*zu. *newSize* ist möglicherweise größer oder kleiner als die Größe des ursprünglich zugeordneten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Wenn der Speicherblock verschoben wird, wird der Inhalt des ursprünglichen Blocks überschrieben.

**_realloc_dbg** legt **errno** auf **ENOMEM** fest, wenn eine Speicher Belegung fehlschlägt oder wenn der benötigte Speicherplatz (einschließlich des bereits erwähnten Mehraufwands) **_HEAP_MAXREQ**überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen über die Belegung, Initialisierung und Verwaltung der Speicherblöcke in der Debugversion des Basisheaps finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_realloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie im Thema [_msize_dbg](msize-dbg.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
