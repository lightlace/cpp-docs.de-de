---
title: _free_dbg
ms.date: 11/04/2016
api_name:
- _free_dbg
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
- _free_dbg
- free_dbg
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
ms.openlocfilehash: 43591ce8710dd25ad33832a5f084ca6e84bba979
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956810"
---
# <a name="_free_dbg"></a>_free_dbg

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
Typ des zugeordneten Speicherblocks, der freigegeben werden soll: **_CLIENT_BLOCK**, **_NORMAL_BLOCK**oder **_IGNORE_BLOCK**.

## <a name="remarks"></a>Hinweise

Die **_free_dbg** -Funktion ist eine Debugversion der [Free](free.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_free_dbg** -Rückruf auf einen **Free**-Befehl reduziert. Sowohl **Free** als auch **_free_dbg** geben einen Speicherblock im Basisheap frei, aber **_free_dbg** bietet zwei Debugfunktionen: die Möglichkeit, freigegebene Blöcke in der verknüpften Liste des Heaps beizubehalten, um Speichermangel zu simulieren, und einen Blocktyp Parameter zu Kostenlose bestimmte Zuordnungs Typen.

**_free_dbg** führt eine Gültigkeits Überprüfung für alle angegebenen Dateien und Blockspeicher Orte aus, bevor der kostenlose Vorgang durchgeführt wird. Die Anwendung stellt diese Informationen wahrscheinlich nicht bereit. Wenn ein Speicherblock freigegeben wird, überprüft der Debugheapmanager automatisch die Pufferintegrität auf beiden Seiten des Benutzerteils und erstellt einen Fehlerbericht, falls über den Puffer hinaus geschrieben wurde. Wenn das **_CRTDBG_DELAY_FREE_MEM_DF** -Bitfeld des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) -Flags festgelegt ist, wird der freigegebene Block mit dem Wert "0xDD" gefüllt, dem **_FREE_BLOCK** -Blocktyp zugewiesen und in der verknüpften Liste von Speicherblöcken des Heaps aufbewahrt.

Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird **errno** mit Informationen aus dem Betriebssystem für die Art des Fehlers festgelegt. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap-Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **_free_dbg**finden Sie unter [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
