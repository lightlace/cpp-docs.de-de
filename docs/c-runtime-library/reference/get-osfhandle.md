---
title: _get_osfhandle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_osfhandle
- _get_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15bddcf3d94935f56fa2e23b6ebd0398ed379c54
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569848"
---
# <a name="getosfhandle"></a>_get_osfhandle

Holt das Betriebssystem-Dateihandle, das dem angegebenen Dateideskriptor zugeordnet ist.

## <a name="syntax"></a>Syntax

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Eine vorhandener Dateideskriptor.

## <a name="return-value"></a>Rückgabewert

Gibt einen Betriebssystem Dateihandle zurück, wenn *fd* gültig ist. Ansonsten wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **INVALID_HANDLE_VALUE** (-1) und legt **Errno** auf **EBADF**, der angibt, eines ungültiges Dateihandle. Um eine compilerwarnung zu vermeiden, wenn das Ergebnis in Routinen verwendet wird, die ein Win32-Dateihandle zu erwarten, wandeln Sie sie in einem **BEHANDELN** Typ.

## <a name="remarks"></a>Hinweise

Um eine Datei zu schließen, deren Dateihandle des Betriebssystems (BS) erhalten, indem Sie **_get_osfhandle**, rufen Sie [_close](close.md) auf den Dateideskriptor *fd*. Rufen Sie nicht **CloseHandle** für den Rückgabewert dieser Funktion. Das zugrunde liegende Betriebssystem-Dateihandle ist im Besitz der *fd* Dateideskriptor und wird geschlossen, wenn [_close](close.md) heißt auf *fd*. Wenn der Dateideskriptor Besitz ist ein **Datei \***  Stream und anschließend durch Aufrufen [Fclose](fclose-fcloseall.md) darauf **Datei \***  Stream schließt sowohl den Dateideskriptor und das zugrunde liegende Betriebssystem-Dateihandle. Rufen Sie in diesem Fall nicht [_close](close.md) auf den Dateideskriptor.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
