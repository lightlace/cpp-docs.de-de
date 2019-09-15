---
title: _CrtMemDifference
ms.date: 11/04/2016
api_name:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: 51bfa014d54f55843fcb112f318f143774abf8f3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938712"
---
# <a name="_crtmemdifference"></a>_CrtMemDifference

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
Zeiger auf eine **_CrtMemState** -Struktur, die zum Speichern der Unterschiede zwischen den beiden Speicher Zuständen (zurückgegeben) verwendet wird.

*oldState*<br/>
Zeiger auf einen früheren Speicher Zustand ( **_CrtMemState** -Struktur).

*newState*<br/>
Zeiger auf einen späteren Speicher Zustand ( **_CrtMemState** -Struktur).

## <a name="return-value"></a>Rückgabewert

Wenn die Speicher Zustände sich erheblich unterscheiden, gibt **_CrtMemDifference** den Wert true zurück. Andernfalls gibt die Funktion FALSE zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtMemDifference** -Funktion vergleicht *oldstate* und *newState* und speichert ihre Unterschiede in *statediff*, die dann von der Anwendung verwendet werden können, um Speicher Verluste und andere Speicherprobleme zu erkennen. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemDifference** während der Vorverarbeitung entfernt.

" *newState* " und " *oldstate* " müssen jeweils ein gültiger Zeiger auf eine **_CrtMemState** -Struktur sein, die in "Crtdbg. h" definiert ist, die von [_CrtMemCheckpoint](crtmemcheckpoint.md) vor dem Aufruf von **_CrtMemDifference**ausgefüllt wurde. *Status FF* muss ein Zeiger auf eine zuvor zugeordnete Instanz der **_CrtMemState** -Struktur sein. Wenn *statediff*, *newState*oder *oldstate* **null**ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) auf **EINVAL** festgelegt, und die Funktion gibt false zurück.

**_CrtMemDifference** vergleicht die **_CrtMemState** -Feldwerte der Blöcke in *oldstate* mit denen in *newState* und speichert das Ergebnis in *statediff*. Wenn sich die Anzahl der zugeordneten Blocktypen oder die Gesamtzahl der zugeordneten Blöcke für jeden Typ in den beiden Speicherzuständen unterscheidet, werden die Zustände als deutlich unterschiedlich bezeichnet. Der Unterschied zwischen dem größten Betrag, der jemals für die beiden Zustände gleichzeitig zugeordnet wurde, und der Unterschied zwischen den Gesamt Zuordnungen für die beiden Zustände wird ebenfalls in *statediff*gespeichert.

Standardmäßig sind interne C-Lauf Zeitblöcke ( **_CRT_BLOCK**) nicht in Speicher Zustands Vorgängen enthalten. Die [_CrtSetDbgFlag](crtsetdbgflag.md) -Funktion kann zum Aktivieren des **_CRTDBG_CHECK_CRT_DF** -Bits von **_crtDbgFlag** verwendet werden, um diese Blöcke in die Erkennung von Lecks und andere Speicher Zustands Vorgänge einzuschließen. Freigegebene Speicherblöcke ( **_FREE_BLOCK**) bewirken nicht, dass **_CrtMemDifference** "true" zurückgibt.

Weitere Informationen zu Heap Zustands Funktionen und der **_CrtMemState** -Struktur finden Sie unter [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
