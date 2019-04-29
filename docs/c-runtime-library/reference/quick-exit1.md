---
title: quick_exit1
ms.date: 11/04/2016
apiname:
- quick_exit
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- quick_exit
- process/quick_exit
- stdlib/quick_exit
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
ms.openlocfilehash: 50f1ee72cce04c2bebc8f7396a2b6fad98301dd7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358033"
---
# <a name="quickexit"></a>quick_exit

Bewirkt eine normale Programmbeendigung.

## <a name="syntax"></a>Syntax

```C
__declspec(noreturn) void quick_exit(
    int status
);
```

### <a name="parameters"></a>Parameter

*Status*<br/>
Der an die Hostumgebung zurückzugebende Statuscode.

## <a name="return-value"></a>Rückgabewert

Die **Quick_exit** Funktion kann nicht an den Aufrufer zurückgeben.

## <a name="remarks"></a>Hinweise

Die **Quick_exit** Funktion bewirkt eine normale programmbeendigung. Es ruft keine Funktionen registriert, indem **von "atexit"**, **_onexit** oder von registrierten Signalhandler der **Signal** Funktion. Verhalten ist undefiniert, wenn **Quick_exit** aufgerufen wird, mehr als nach, und wenn die **beenden** Funktion wird auch aufgerufen werden.

Die **Quick_exit** Funktionsaufrufe, in der Last in, First Out (LIFO)-Auftrag, indem registrierten Funktionen **At_quick_exit**, außer dass für diese Funktionen bereits wird aufgerufen, wenn die Funktion registriert wurde.  Da Verhalten ist undefiniert, wenn ein [longjmp](longjmp.md) -Aufruf während des Aufrufs einer registrierten Funktion erfolgt, die den Aufruf der Funktion beenden würde.

Nachdem die registrierten Funktionen aufgerufen wurden, **Quick_exit** aufruft **_Exit** mithilfe der *Status* Wert, um die Steuerung an die hostumgebung zurückzugeben.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**quick_exit**|\<process.h> oder\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec- und _wexec-Funktionen](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn-, _wspawn-Funktionen](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
