---
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
api_name:
- _CrtDumpMemoryLeaks
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
ms.openlocfilehash: dae93577f5c0c0297606577c05d6b6ef2040c831
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938827"
---
# <a name="_crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

Legt alle Speicherblöcke im Debugheap ab, wenn ein Speicherverlust aufgetreten ist (nur Debugversion).

## <a name="syntax"></a>Syntax

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>Rückgabewert

**_CrtDumpMemoryLeaks** gibt true zurück, wenn ein Speicherlecks gefunden wird. Andernfalls gibt die Funktion FALSE zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtDumpMemoryLeaks** -Funktion bestimmt, ob seit dem Start der Programmausführung ein Speicherfehler aufgetreten ist. Wenn ein Verlust erkannt wird, werden die Debugheaderinformationen für alle Objekte im Heap in einer für den Benutzer lesbaren Form ausgegeben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtDumpMemoryLeaks** während der Vorverarbeitung entfernt.

**_CrtDumpMemoryLeaks** wird häufig am Ende der Programmausführung aufgerufen, um zu überprüfen, ob der gesamte von der Anwendung zugewiesene Arbeitsspeicher freigegeben wurde. Die-Funktion kann bei der Programm Beendigung automatisch aufgerufen werden, indem das **_CRTDBG_LEAK_CHECK_DF** -Bitfeld des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) -Flags mithilfe der [_CrtSetDbgFlag](crtsetdbgflag.md) -Funktion eingeschaltet wird.

**_CrtDumpMemoryLeaks** ruft [_CrtMemCheckpoint](crtmemcheckpoint.md) auf, um den aktuellen Zustand des Heaps abzurufen, und scannt dann den Zustand auf Blöcke, die nicht freigegeben wurden. Wenn ein nicht frei gegebener Block gefunden wird, ruft **_CrtDumpMemoryLeaks** [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) auf, um Informationen für alle Objekte zu sichern, die vom Beginn der Programmausführung im Heap zugeordnet wurden.

Standardmäßig sind interne C-Lauf Zeitblöcke ( **_CRT_BLOCK**) nicht in Speicher Abbild Vorgängen enthalten. Die [_CrtSetDbgFlag](crtsetdbgflag.md) -Funktion kann zum Aktivieren des **_CRTDBG_CHECK_CRT_DF** -Bits von **_crtDbgFlag** verwendet werden, um diese Blöcke in den Prozess zur Erkennung von Lecks einzubeziehen.

Weitere Informationen zu Heap Zustands Funktionen und der **_CrtMemState** -Struktur finden Sie unter [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **_CrtDumpMemoryLeaks**finden Sie unter [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
