---
title: _aligned_offset_malloc_dbg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: afb15a5e132d70b40fa3e816f5271a192df5788a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*Ausrichtung*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*offset*<br/>
Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.

*filename*<br/>
Zeiger zum Namen der Quelldatei, der die Belegung angefordert hat, oder NULL.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder NULL.

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Speicherblock, der belegt wurde oder **NULL** bei fehlgeschlagenem Vorgang.

## <a name="remarks"></a>Hinweise

**_aligned_offset_malloc_dbg** ist eine Debugversion der [_aligned_offset_malloc](aligned-offset-malloc.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, bei jedem Aufruf **_aligned_offset_malloc_dbg** wird zu einem Aufruf von reduziert **_aligned_offset_malloc**. Beide **_aligned_offset_malloc** und **_aligned_offset_malloc_dbg** belegen einen Speicherblock im Basisheap, jedoch **_aligned_offset_malloc_dbg** bietet mehrere Debugfunktionen: Puffer auf beiden Seiten des benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen blocktypparameter zum Nachverfolgen von bestimmten belegungstypen und *Filename*/*Linenumber* Informationen zum Ermitteln des Ursprungs von belegungsanforderungen.

**_aligned_offset_malloc_dbg** belegt den Speicherblock mit etwas mehr Speicherplatz als der angeforderten *Größe*. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.

**_aligned_offset_malloc_dbg** eignet sich für Situationen, in denen eine Ausrichtung für ein geschachteltes Element; erforderlich ist z. B., wenn eine Ausrichtung für eine geschachtelte Klasse erforderlich war.

**_aligned_offset_malloc_dbg** basiert auf **"malloc"**; Weitere Informationen finden Sie unter ["malloc"](malloc.md).

Diese Funktion legt **Errno** auf **ENOMEM** , wenn die speicherbelegung fehlgeschlagen ist oder wenn die angeforderte Größe größer war **_HEAP_MAXREQ**. Weitere Informationen zu **Errno**, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus **_aligned_offset_malloc** überprüft die eigenen Parameter. Wenn *Ausrichtung* Potenz von 2 ist oder wenn *Offset* ist größer als oder gleich *Größe* und ungleich NULL ist, ruft diese Funktion den Handler für ungültige Parameter wie beschrieben in [ Überprüfen der Parameter](../../c-runtime-library/parameter-validation.md). Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **NULL** und legt **Errno** auf **EINVAL**.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
