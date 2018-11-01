---
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
ms.openlocfilehash: baf4f8d8234ba744acda20541d37bbc3ed076678
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531967"
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

Legt alle Speicherblöcke im Debugheap ab, wenn ein Speicherverlust aufgetreten ist (nur Debugversion).

## <a name="syntax"></a>Syntax

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>Rückgabewert

**_CrtDumpMemoryLeaks** gibt TRUE zurück, wenn ein Speicherverlust erkannt wird. Andernfalls gibt die Funktion FALSE zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtDumpMemoryLeaks** Funktion bestimmt, ob seit dem Beginn der programmausführung ein Speicherverlust aufgetreten ist. Wenn ein Verlust erkannt wird, werden die Debugheaderinformationen für alle Objekte im Heap in einer für den Benutzer lesbaren Form ausgegeben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtDumpMemoryLeaks** werden während der vorverarbeitung entfernt.

**_CrtDumpMemoryLeaks** wird häufig aufgerufen werden, am Ende der Ausführung des Programms stellen Sie sicher, dass alle von der Anwendung belegten Arbeitsspeicher freigegeben wurde. Die Funktion kann aufgerufen werden automatisch bei Beendigung des Programms durch Aktivieren der **_CRTDBG_LEAK_CHECK_DF** -Bitfeld des der [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) Flags mithilfe der [_CrtSetDbgFlag](crtsetdbgflag.md)Funktion.

**_CrtDumpMemoryLeaks** Aufrufe [_CrtMemCheckpoint](crtmemcheckpoint.md) auf den aktuellen Zustand des Heaps abzurufen und sucht dann in den Zustand für Speicherblöcke, die nicht freigegeben wurden. Bei ein-Blocks auftreten **_CrtDumpMemoryLeaks** Aufrufe [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) um Informationen für alle Objekte, die seit dem Beginn der programmausführung im Heap zugeordnet.

Standardmäßig sind interne C-laufzeitblöcke (**_CRT_BLOCK**) sind nicht in speicherabbildvorgängen enthalten. Die [_CrtSetDbgFlag](crtsetdbgflag.md) Funktion kann verwendet werden, zum Aktivieren der **_CRTDBG_CHECK_CRT_DF** -Bit von **_crtDbgFlag** um diese Blöcke bei der Erkennung von Speicherverlusten einzuschließen.

Weitere Informationen über heapzustandsfunktionen und die **_CrtMemState** Struktur, siehe [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung **_CrtDumpMemoryLeaks**, finden Sie unter [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
