---
title: _recalloc_dbg
ms.date: 11/04/2016
api_name:
- _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
ms.openlocfilehash: 6274e749b2c4e6f64c7c7f82f8764dcf5ba642fe
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949477"
---
# <a name="_recalloc_dbg"></a>_recalloc_dbg

Ordnet ein Array neu zu und initialisiert seine Elemente auf 0 (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void *_recalloc_dbg(
   void *userData,
   size_t num,
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*userData*<br/>
Zeiger zum vorherigen belegten Speicherblock.

*number*<br/>
Angeforderte Anzahl von Speicherblöcken.

*size*<br/>
Angeforderte Größe eines Speicherblocks (Bytes).

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den Zuordnungs Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der Zuordnungs Vorgang angefordert wurde, oder **null**.

Die Parameter " *filename* " und " *LineNumber* " sind nur verfügbar, wenn " **_recalloc_dbg** " explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) -präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Nach erfolgreichem Abschluss gibt diese Funktion entweder einen Zeiger auf den Benutzer Teil des neu belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt **null**zurück. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [_recalloc](recalloc.md)-Funktion.

## <a name="remarks"></a>Hinweise

**_recalloc_dbg** ist eine Debugversion der [_recalloc](recalloc.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_recalloc_dbg** -Rückruf auf einen **_recalloc**-aufrufenden Wert reduziert. Sowohl **_recalloc** als auch **_recalloc_dbg** ordnen einen Speicherblock im Basisheap neu zu, **_recalloc_dbg** bietet jedoch mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzer Teils des Blocks zum Prüfen auf Speicher Verluste, einen Blocktyp Parameter. zum Nachverfolgen spezifischer Zuordnungs Typen und *Dateiname*/*LineNumber* -Informationen, um den Ursprung von Zuordnungs Anforderungen zu bestimmen.

**_recalloc_dbg** ordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die angeforderte Größe (*Zahlen* * *Größe*) neu zu, die größer oder kleiner als die Größe des ursprünglich zugeordneten Speicherblocks sein kann. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Der Benutzerteil des Blocks wird mit dem Wert 0xCD gefüllt, und jeder der Überschreibungspuffer wird mit 0xFD gefüllt.

**_recalloc_dbg** legt **errno** auf **den** Wert fest, wenn eine Speicher Belegung fehlschlägt. " **EINVAL** " wird zurückgegeben, wenn der benötigte Speicherplatz (einschließlich des bereits erwähnten Mehraufwands) **_HEAP_MAXREQ**überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debugheapdetails](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_recalloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
