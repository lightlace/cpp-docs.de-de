---
title: _CrtMemDifference
ms.date: 11/04/2016
apiname:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: f2c6306bf604737d0ace142674b21845a08e2dee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429652"
---
# <a name="crtmemdifference"></a>_CrtMemDifference

Vergleicht zwei Speicherzustände und gibt die vorhandenen Unterschiede zurück (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>Parameter

*stateDiff*<br/>
Zeiger auf eine **_CrtMemState** -Struktur, die verwendet wird, um die Unterschiede zwischen den beiden Speicherzuständen (Rückgabewert) zu speichern.

*oldState*<br/>
Zeiger auf einen früheren Speicherzustand (**_CrtMemState** Struktur).

*newState*<br/>
Zeiger auf einen späteren Speicherzustand (**_CrtMemState** Struktur).

## <a name="return-value"></a>Rückgabewert

Wenn die Speicherzustände unterscheiden sich grundlegend, **_CrtMemDifference** gibt TRUE zurück. Andernfalls gibt die Funktion FALSE zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtMemDifference** -Funktion vergleicht *OldState* und *NewState* und speichert die vorhandenen Unterschiede in *StateDiff*, dann können die von der Anwendung verwendet werden, um Speicherverluste und andere Speicherprobleme zu erkennen. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemDifference** werden während der vorverarbeitung entfernt.

*NewState* und *OldState* muss jeweils ein gültiger Zeiger auf eine **_CrtMemState** in "CRTDBG.h" definiert, die von gefüllt wurde definierte Struktur [_CrtMemCheckpoint](crtmemcheckpoint.md)vor dem Aufruf **_CrtMemDifference**. *StateDiff* muss ein Zeiger auf eine zuvor zugeordnete Instanz von der **_CrtMemState** Struktur. Wenn *StateDiff*, *NewState*, oder *OldState* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [ Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) nastaven NA hodnotu **EINVAL** und die Funktion gibt "false" zurück.

**_CrtMemDifference** vergleicht die **_CrtMemState** -Feldwerte der Blöcke in *OldState* , die denen in *NewState* und speichert das Ergebnis in *StateDiff*. Wenn sich die Anzahl der zugeordneten Blocktypen oder die Gesamtzahl der zugeordneten Blöcke für jeden Typ in den beiden Speicherzuständen unterscheidet, werden die Zustände als deutlich unterschiedlich bezeichnet. Der Unterschied zwischen der größten Menge, die jemals gleichzeitig zugeordnet wurde für die beiden Zustände und den Unterschied zwischen den gesamten speicherbelegungen für die beiden Zustände als auch gespeichert *StateDiff*.

Standardmäßig sind interne C-laufzeitblöcke (**_CRT_BLOCK**) nicht in speicherzustandsvorgänge enthalten sind. Die [_CrtSetDbgFlag](crtsetdbgflag.md) Funktion kann verwendet werden, zum Aktivieren der **_CRTDBG_CHECK_CRT_DF** -Bit von **_crtDbgFlag** Erkennung von Speicherverlusten und anderen Speicherzustand diesen Blöcken einschließt Vorgänge. Freigegebene Speicherblöcke (**_FREE_BLOCK**) verursachen kein **_CrtMemDifference** auf "true" zurückgeben.

Weitere Informationen über heapzustandsfunktionen und die **_CrtMemState** Struktur, siehe [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
