---
title: _recalloc_dbg
ms.date: 11/04/2016
apiname:
- _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
ms.openlocfilehash: e2782492d3338b5b548db0153b6123fb82ff5e72
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653270"
---
# <a name="recallocdbg"></a>_recalloc_dbg

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

*Anzahl*<br/>
Angeforderte Anzahl von Speicherblöcken.

*size*<br/>
Angeforderte Größe eines Speicherblocks (Bytes).

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die Belegung angefordert oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in denen Belegung angefordert wurde, oder **NULL**.

Die *Filename* und *Linenumber* Parameter sind nur verfügbar, wenn **_recalloc_dbg** explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) Präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreichem Abschluss diese Funktion gibt einen Zeiger an den benutzerteil des neu belegten Speicherblocks zurück, ruft die neue Handlerfunktion, oder gibt zurück, **NULL**. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [_recalloc](recalloc.md)-Funktion.

## <a name="remarks"></a>Hinweise

**_recalloc_dbg** ist eine Debugversion von der [_recalloc](recalloc.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, jeden Aufruf von **_recalloc_dbg** wird nach einer Verkleinerung auf einen Aufruf von **_recalloc**. Beide **_recalloc** und **_recalloc_dbg** zum erneuten Zuweisen eines Speicherblocks im Basisheap, jedoch **_recalloc_dbg** Datenbankmodell kann mehrere Debugfunktionen: Puffer auf beiden Seiten Geben Sie Parameter zum Nachverfolgen bestimmter belegungstypen des benutzerteils des Blocks zum Prüfen auf Speicherverluste, ein Block und *Filename*/*Linenumber* -Informationen zum Ermitteln der Ursprungs von belegungsanforderungen.

**_recalloc_dbg** zuordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die angeforderte Größe (*Anzahl* * *Größe*) größer oder kleiner als die Größe des sein kann der ursprünglich zugeordneten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Der Benutzerteil des Blocks wird mit dem Wert 0xCD gefüllt, und jeder der Überschreibungspuffer wird mit 0xFD gefüllt.

**_recalloc_dbg** legt **Errno** zu **ENOMEM** , wenn eine speicherbelegung fehlschlägt. **EINVAL** wird zurückgegeben, wenn der Umfang des erforderlichen Arbeitsspeichers (einschließlich der bereits erwähnten Mehraufwands) überschreitet **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

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
