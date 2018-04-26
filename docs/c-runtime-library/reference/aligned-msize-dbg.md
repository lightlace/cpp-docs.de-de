---
title: _aligned_msize_dbg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef63ea4ebd41026d548952aa6ec29749bcc55245
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg

Gibt die Größe eines im Heap belegten Speicherblocks zurück (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
size_t _aligned_msize_dbg(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Zeiger zum Speicherblock.

*Ausrichtung*<br/>
Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.

*offset*<br/>
Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.

## <a name="return-value"></a>Rückgabewert

Gibt die Größe (in Bytes) als ganze Zahl ohne Vorzeichen zurück.

## <a name="remarks"></a>Hinweise

Die *Ausrichtung* und *Offset* Werte müssen identisch sein, die die Werte für die Funktion, die den Speicherblock belegt übergeben.

**_aligned_msize_dbg** ist eine Debugversion der [_aligned_msize](aligned-msize.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, bei jedem Aufruf **_aligned_msize_dbg** wird zu einem Aufruf von reduziert **_aligned_msize**. Beide **_aligned_msize** und **_aligned_msize_dbg** berechnen Sie die Größe eines Speicherblocks im Basisheap, jedoch **_aligned_msize_dbg** Fügt eine Debugfunktion: er enthält die Puffer auf beiden Seiten des benutzerteils des Arbeitsspeichers-block in der zurückgegebenen Größe.

Diese Funktion überprüft seine Parameter. Wenn *Memblock* ist ein null-Zeiger oder *Ausrichtung* ist keine Potenz von 2, **_msize** wird einen Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung ](../../c-runtime-library/parameter-validation.md). Wenn der Fehler behandelt wird, setzt der Funktion **Errno** auf **EINVAL** und gibt-1 zurück.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
