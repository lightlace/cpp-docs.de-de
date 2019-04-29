---
title: _get_osfhandle
ms.date: 05/29/2018
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
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: beab4e4308bc7bcde287366b78671f61a89f8827
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332207"
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

Gibt einen Betriebssystem-Dateihandle zurück, wenn *fd* gültig ist. Ansonsten wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Diese Funktion gibt zurück, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **INVALID_HANDLE_VALUE** (-1) und legt **Errno** zu **EBADF**, der angibt, eines ungültigen Dateihandles. Um eine compilerwarnung zu vermeiden, wenn das Ergebnis in Routinen verwendet wird, die ein Win32-Dateihandle zu erwarten, wandeln Sie sie in einem **BEHANDELN** Typ.

## <a name="remarks"></a>Hinweise

Um eine Datei zu schließen, dessen Betriebssystem (OS)-Datei-Handle, indem abgerufen wird **_get_osfhandle**, rufen Sie [_close](close.md) auf den Dateideskriptor *fd*. Rufen Sie keine **"CloseHandle"** für den Rückgabewert dieser Funktion. Das zugrunde liegende Betriebssystem-Dateihandle ist im Besitz der *fd* Dateideskriptor und wird geschlossen, wenn [_close](close.md) heißt auf *fd*. Wenn der Dateideskriptor Besitz ist eine `FILE *` Stream, rufen Sie dann [Fclose](fclose-fcloseall.md) , `FILE *` Stream geschlossen wird, sowohl der Dateideskriptor und das zugrunde liegende Betriebssystem-Dateihandle. Rufen Sie in diesem Fall nicht [_close](close.md) auf den Dateideskriptor.

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
