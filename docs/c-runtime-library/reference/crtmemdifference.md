---
title: _CrtMemDifference | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66bb770c2f24c0312277d23c14beef09e2265f88
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398047"
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
Zeiger auf eine **_CrtMemState** -Struktur, die zum Speichern der Unterschiede zwischen den beiden (zurückgegebenen) Speicherzuständen verwendet wird.

*oldState*<br/>
Zeiger auf einen früheren Speicherzustand (**_CrtMemState** Struktur).

*newState*<br/>
Zeiger auf einen späteren Speicherzustand (**_CrtMemState** Struktur).

## <a name="return-value"></a>Rückgabewert

Wenn die Speicherzustände unterscheiden sich deutlich, **_CrtMemDifference** gibt "true" zurück. Andernfalls gibt die Funktion FALSE zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtMemDifference** -Funktion vergleicht *OldState* und *NewState* und speichert die vorhandenen Unterschiede in *StateDiff*, dann können die von der Anwendung verwendet werden, um Speicherverluste und andere Speicherprobleme zu erkennen. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemDifference** während der vorverarbeitung entfernt.

*NewState* und *OldState* muss jeweils ein gültiger Zeiger auf eine **_CrtMemState** Struktur, die in "CRTDBG.h", die von gefüllt wurde definiert [_CrtMemCheckpoint](crtmemcheckpoint.md)vor dem Aufruf **_CrtMemDifference**. *StateDiff* muss ein Zeiger auf eine zuvor zugeordnete Instanz von der **_CrtMemState** Struktur. Wenn *StateDiff*, *NewState*, oder *OldState* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [ Überprüfen der Parameter](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) festgelegt ist, um **EINVAL** und die Funktion gibt "false" zurück.

**_CrtMemDifference** vergleicht die **_CrtMemState** -Feldwerte der Blöcke in *OldState* , die unter *NewState* und speichert das Ergebnis in *StateDiff*. Wenn sich die Anzahl der zugeordneten Blocktypen oder die Gesamtzahl der zugeordneten Blöcke für jeden Typ in den beiden Speicherzuständen unterscheidet, werden die Zustände als deutlich unterschiedlich bezeichnet. Der Unterschied zwischen der größten Menge, die jemals gleichzeitig zugeordnet wurde für die beiden Zustände und den Unterschied zwischen den gesamten speicherbelegungen für die beiden Zustände werden auch in gespeichert *StateDiff*.

Standardmäßig sind interne C-laufzeitblöcke (**_CRT_BLOCK**) sind nicht in den speicherzustandsvorgängen enthalten. Die [_CrtSetDbgFlag](crtsetdbgflag.md) -Funktion kann verwendet werden, zum Aktivieren der **_CRTDBG_CHECK_CRT_DF** -Bit von **_crtDbgFlag** Erkennung von Speicherverlusten und andere Speicherzustands diese Blöcke einschließt DDL-Vorgänge. Freigegebene Speicherblöcke (**_FREE_BLOCK**) führen nicht dazu, dass **_CrtMemDifference** "Wahr" zurückgegeben.

Weitere Informationen über heapzustandsfunktionen und die **_CrtMemState** -Struktur, finden Sie unter [den Heapzustand](/visualstudio/debugger/crt-debug-heap-details). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
