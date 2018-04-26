---
title: _recalloc_dbg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 78246b18a5706d5f69990c01bac473587be5c62a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*Benutzerdaten*<br/>
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
Zeilennummer in der Quelldatei, in die Belegung angefordert wurde, oder **NULL**.

Die *Filename* und *Linenumber* -Parameter sind nur verfügbar, wenn **_recalloc_dbg** explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) -Präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreichem Abschluss gibt diese Funktion entweder einen Zeiger an den Benutzerteil des neu belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt NULL zurück. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [_recalloc](recalloc.md)-Funktion.

## <a name="remarks"></a>Hinweise

**_recalloc_dbg** ist eine Debugversion der [_recalloc](recalloc.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, bei jedem Aufruf **_recalloc_dbg** wird zu einem Aufruf von reduziert **_recalloc**. Beide **_recalloc** und **_recalloc_dbg** weisen einen Speicherblock im Basisheap, jedoch **_recalloc_dbg** hat mehrere Debugfunktionen: Puffer auf beiden Seiten Geben Sie Parameter zum Nachverfolgen von bestimmten belegungstypen des benutzerteils des Blocks zum Prüfen auf Speicherverluste, ein Block und *Filename*/*Linenumber* -Informationen zum Ermitteln der Ursprungs von belegungsanforderungen.

**_recalloc_dbg** ordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die angeforderte Größe (*Anzahl* * *Größe*) größer oder kleiner als die Größe des sein die ursprünglich belegten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Der Benutzerteil des Blocks wird mit dem Wert 0xCD gefüllt, und jeder der Überschreibungspuffer wird mit 0xFD gefüllt.

**_recalloc_dbg** legt **Errno** auf **ENOMEM** Wenn eine speicherbelegung fehlschlägt. **EINVAL** wird zurückgegeben, wenn der Speicherplatz (einschließlich der bereits erwähnten Mehraufwands) übersteigt die **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debugheapdetails](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_recalloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
