---
title: _aligned_free_dbg
ms.date: 11/04/2016
apiname:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
ms.openlocfilehash: f51b9b9573ab2e23a0a60979c55a33d2e5cff747
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341898"
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg

Gibt einen Speicherblock frei, der mit [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) belegt ist (nur in der Debugversion).

## <a name="syntax"></a>Syntax

```C
void _aligned_free_dbg(
   void *memblock
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Ein Zeiger auf den Speicherblock, die zurückgegeben wurde, die [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) Funktion.

## <a name="remarks"></a>Hinweise

Die **_aligned_free_dbg** -Funktion ist eine Debugversion der [_aligned_free](aligned-free.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, jeden Aufruf von **_aligned_free_dbg** wird nach einer Verkleinerung auf einen Aufruf von `_aligned_free`. Beide `_aligned_free` und **_aligned_free_dbg** geben einen Speicherblock im Basisheap, jedoch **_aligned_free_dbg** ermöglicht eine Debugfunktion: die Möglichkeit, um Speichermangel zu halten, freigegebene Blöcke in der verknüpften Liste des Heaps simulieren Sie Bedingungen mit unzureichendem Arbeitsspeicher.

**_aligned_free_dbg** führt eine gültigkeitsüberprüfung für alle angegebenen Dateien und blockspeicherorte, bevor Sie eine Freigabe erfolgt. Die Anwendung stellt diese Informationen wahrscheinlich nicht bereit. Wenn ein Speicherblock freigegeben wird, überprüft der Debugheapmanager automatisch die Pufferintegrität auf beiden Seiten des Benutzerteils und erstellt einen Fehlerbericht, falls über den Puffer hinaus geschrieben wurde. Wenn die _CRTDBG_DELAY_FREE_MEM_DF--Feld Bit der [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) Flags festgelegt ist, wird der freigegebene Block mit dem Wert "0xDD" gefüllt, die _FREE_BLOCK-Block-Datentyp zugewiesen und in der verknüpften Liste von Speicherblöcken beibehalten wird.

Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap-Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)