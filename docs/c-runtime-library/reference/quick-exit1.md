---
title: quick_exit1
ms.date: 11/04/2016
api_name:
- quick_exit
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- quick_exit
- process/quick_exit
- stdlib/quick_exit
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
ms.openlocfilehash: 86246ed7a32dcd2f12b38aa4148570fc5fb3b7a6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949665"
---
# <a name="quick_exit"></a>quick_exit

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

Die **quick_exit** -Funktion kann nicht zum Aufrufer zurückkehren.

## <a name="remarks"></a>Hinweise

Die **quick_exit** -Funktion bewirkt eine normale Programm Beendigung. Er ruft keine Funktionen auf, die von **atexit**, **_onexit** oder Signal Handlern registriert werden, die von der **Signal** -Funktion registriert wurden. Das Verhalten ist nicht definiert, wenn **quick_exit** mehrmals aufgerufen wird oder wenn die **Exit** -Funktion ebenfalls aufgerufen wird.

Die **quick_exit** -Funktion ruft in der LIFO-Reihenfolge (Last in, First Out) die von **at_quick_exit**registrierten Funktionen ab, mit Ausnahme der Funktionen, die bereits beim Registrieren der Funktion aufgerufen wurden.  Da Verhalten ist undefiniert, wenn ein [longjmp](longjmp.md) -Aufruf während des Aufrufs einer registrierten Funktion erfolgt, die den Aufruf der Funktion beenden würde.

Nachdem die registrierten Funktionen aufgerufen wurden, ruft **quick_exit** **_Exit** auf, indem der *Status* Wert verwendet wird, um die Steuerung an die Host Umgebung zurückzugeben.

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
