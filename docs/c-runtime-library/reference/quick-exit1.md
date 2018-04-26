---
title: quick_exit1 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fde06fc83b27b8bba43e3fa929cc8b97bb68dd06
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*status*<br/>
Der an die Hostumgebung zurückzugebende Statuscode.

## <a name="return-value"></a>Rückgabewert

Die **Quick_exit** -Funktion kann nicht an den Aufrufer zurückgeben.

## <a name="remarks"></a>Hinweise

Die **Quick_exit** Funktion bewirkt eine normale programmbeendigung. Sie ruft keine registriert, indem Sie Funktionen **Atexit**, **_onexit** oder vom registrierten Signalhandler der **Signal** Funktion. Verhalten ist undefiniert, wenn **Quick_exit** aufgerufen wird, mehr als nach, und wenn die **beenden** Funktion wird auch aufgerufen.

Die **Quick_exit** Funktionsaufrufe in Last in, First Out (LIFO)-Auftrag, die von registrierten Funktionen **At_quick_exit**, abgesehen von den für diese Funktionen bereits wird aufgerufen, wenn die Funktion registriert wurde.  Das Verhalten ist undefiniert, wenn ein [longjmp](longjmp.md)-Aufruf während des Aufrufs einer registrierten Funktion erfolgt, die den Aufruf der Funktion beenden würde.

Nachdem die registrierten Funktionen aufgerufen wurden, **Quick_exit** ruft **_Exit** mithilfe der *Status* Wert, um die Steuerung an die hostumgebung zurückzugeben.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
