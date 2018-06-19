---
title: _aligned_free_dbg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88c7eb281ecc7a7175614c5c72c54c7267cf55e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393458"
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

*Memblock* einen Zeiger zum Speicherblock, der an zurückgegeben wurde die [_aligned_malloc](aligned-malloc.md) oder [_aligned_offset_malloc](aligned-offset-malloc.md) Funktion.

## <a name="remarks"></a>Hinweise

Die **_aligned_free_dbg** Funktion ist eine Debugversion der [_aligned_free](aligned-free.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, bei jedem Aufruf **_aligned_free_dbg** wird zu einem Aufruf von reduziert **_aligned_free**. Beide **_aligned_free** und **_aligned_free_dbg** frei einen Speicherblock im Basisheap, jedoch **_aligned_free_dbg** hat eine Debugfunktion: die Möglichkeit, freigegebene beibehalten Blöcke in der verknüpften Heapliste um Speichermangel zu simulieren.

**_aligned_free_dbg** führt eine gültigkeitsüberprüfung für alle angegebenen Dateien und blockspeicherorte vor dem Ausführen des Vorgangs frei. Die Anwendung stellt diese Informationen wahrscheinlich nicht bereit. Wenn ein Speicherblock freigegeben wird, überprüft der Debugheapmanager automatisch die Pufferintegrität auf beiden Seiten des Benutzerteils und erstellt einen Fehlerbericht, falls über den Puffer hinaus geschrieben wurde. Wenn die **_CRTDBG_DELAY_FREE_MEM_DF** -Bitfeld des der [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) Flags festgelegt ist, wird der freigegebene Block mit den zugewiesenen Wert 0xDD, gefüllt der **_FREE_BLOCK** Blocktyp, und in der verknüpften Heapliste von Speicherblöcken aufbewahrt wird.

Wenn ein Fehler auftritt, bei der Freigabe des Arbeitsspeichers und **Errno** mit Informationen des Betriebssystems über die Art des Fehlers festgelegt ist. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap-Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
