---
title: _free_dbg
ms.date: 11/04/2016
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
ms.openlocfilehash: 5a0024101e4f5a74f1573b271d444b27738db8e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442245"
---
# <a name="freedbg"></a>_free_dbg

Gibt einen Speicherblock im Heap frei (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void _free_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>Parameter

*userData*<br/>
Zeiger zum belegten Speicherblock, der freigegeben werden soll.

*blockType*<br/>
Typ des belegten Speicherblock freigegeben werden: **_CLIENT_BLOCK**, **_NORMAL_BLOCK**, oder **_IGNORE_BLOCK**.

## <a name="remarks"></a>Hinweise

Die **_free_dbg** -Funktion ist eine Debugversion der der [kostenlose](free.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, jeden Aufruf von **_free_dbg** wird nach einer Verkleinerung auf einen Aufruf von **kostenlose**. Beide **kostenlose** und **_free_dbg** geben einen Speicherblock im Basisheap, jedoch **_free_dbg** unterstützt zwei Debugfunktionen: die Möglichkeit, um Speichermangel zu halten, freigegebene Blöcke in des Heaps verknüpfte Liste, um Bedingungen mit unzureichendem Arbeitsspeicher und einen blocktypparameter zum Freigeben bestimmter belegungstypen zu simulieren.

**_free_dbg** führt eine gültigkeitsüberprüfung für alle angegebenen Dateien und blockspeicherorte, bevor Sie eine Freigabe erfolgt. Die Anwendung stellt diese Informationen wahrscheinlich nicht bereit. Wenn ein Speicherblock freigegeben wird, überprüft der Debugheapmanager automatisch die Pufferintegrität auf beiden Seiten des Benutzerteils und erstellt einen Fehlerbericht, falls über den Puffer hinaus geschrieben wurde. Wenn die **_CRTDBG_DELAY_FREE_MEM_DF** -Bitfeld des der [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) -Flag festgelegt ist, wird der freigegebene Block mit den zugewiesenen Wert "0xDD", gefüllt der **_FREE_BLOCK** Blocktyp, und in der verknüpften Liste von Speicherblöcken aufbewahrt wird.

Wenn ein Fehler auftritt, bei der Freigabe von Speicher **Errno** mit Informationen aus dem Betriebssystem von der Art des Fehlers festgelegt ist. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap-Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung **_free_dbg**, finden Sie unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
