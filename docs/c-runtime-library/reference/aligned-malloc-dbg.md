---
title: _aligned_malloc_dbg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _aligned_malloc_dbg
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
- _aligned_malloc_dbg
- aligned_malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_malloc_dbg function
- _aligned_malloc_dbg function
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9208436fe68896a7a1811eab64d28cdbb3f3c221
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="alignedmallocdbg"></a>_aligned_malloc_dbg

Belegt einen Speicherblock in einer angegebenen Ausrichtungsgrenze mit zusätzlichem Speicherplatz für einen Debugheader und Überschreibungspuffer (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void * _aligned_malloc_dbg(
    size_t size,
    size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Größe der angeforderten Speicherzuweisung.

*Ausrichtung*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*filename*<br/>
Zeiger zum Namen der Quelldatei, der die Belegung angefordert hat, oder NULL.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder NULL.

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Speicherblock, der belegt wurde oder **NULL** bei fehlgeschlagenem Vorgang.

## <a name="remarks"></a>Hinweise

**_aligned_malloc_dbg** ist eine Debugversion der [_aligned_malloc](aligned-malloc.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, bei jedem Aufruf **_aligned_malloc_dbg** wird zu einem Aufruf von reduziert **_aligned_malloc**. Beide **_aligned_malloc** und **_aligned_malloc_dbg** belegen einen Speicherblock im Basisheap, jedoch **_aligned_malloc_dbg** bietet mehrere Debugfunktionen: Puffer auf beiden Seiten des benutzerteils des Blocks zum Prüfen auf Speicherverluste und *Filename*/*Linenumber* Informationen zum Ermitteln des Ursprungs von belegungsanforderungen.

**_aligned_malloc_dbg** belegt den Speicherblock mit etwas mehr Speicherplatz als der angeforderten *Größe*. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.

**_aligned_malloc_dbg** legt **Errno** auf **ENOMEM** , wenn eine speicherbelegung fehlschlägt oder wenn der benötigte Speicherplatz (einschließlich der bereits erwähnten Mehraufwands) überschreitet **_ HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus **_aligned_malloc_dbg** überprüft die eigenen Parameter. Wenn *Ausrichtung* ist keine Potenz von 2 oder *Größe* NULL ist, ruft diese Funktion den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **NULL** und legt **Errno** auf **EINVAL**.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_malloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
