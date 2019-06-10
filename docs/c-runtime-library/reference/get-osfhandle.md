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
ms.openlocfilehash: cc3b50e3d3f65bee83b8df83aa0adb5c8694e35a
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821657"
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

Gibt einen Betriebssystem-Dateihandle zurück, wenn *fd* gültig ist. Ansonsten wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, gibt es **INVALID_HANDLE_VALUE** (-1). Außerdem wird **Errno** zu **EBADF**, der angibt, eines ungültigen Dateihandles. Um eine Warnung zu vermeiden, wenn das Ergebnis als ein Win32-Dateihandle verwendet wird, wandeln Sie sie in einem **BEHANDELN** Typ.

> [!NOTE]
> Wenn **Stdin**, **"stdout"** , und **"stderr"** werden keinem Stream (z. B. in einer Windows-Anwendung ohne ein Konsolenfenster), die Werte für die Datei Deskriptor zugeordnet Diese Streams werden zurückgegeben, aus [_fileno](fileno.md) als den speziellen Wert-2. Auf ähnliche Weise, wenn Sie als den File-Deskriptor-Parameter, anstatt das Ergebnis eines Aufrufs von 0, 1 oder 2 verwenden **_fileno**, **_get_osfhandle** gibt auch den speziellen Wert-2 zurück, wenn der Dateideskriptor nicht verknüpft ist. mit einem Datenstrom und nicht **Errno**. Aber dies ist nicht der Wert eine gültige Datei Handles, und nachfolgende Aufrufe, die versuchen, die sie verwenden, treten wahrscheinlich Fehler auf.

Weitere Informationen zu **EBADF** und andere Fehlercodes finden Sie unter [_doserrno, Errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Um eine Datei zu schließen, dessen Betriebssystem (OS)-Datei-Handle, indem abgerufen wird **_get_osfhandle**, rufen Sie [_close](close.md) auf den Dateideskriptor *fd*. Rufen Sie nie **"CloseHandle"** für den Rückgabewert dieser Funktion. Das zugrunde liegende Betriebssystem-Dateihandle ist im Besitz der *fd* Dateideskriptor und wird geschlossen, wenn [_close](close.md) heißt auf *fd*. Wenn der Dateideskriptor Besitz ist eine `FILE *` Stream, rufen Sie dann [Fclose](fclose-fcloseall.md) , `FILE *` Stream geschlossen wird, sowohl der Dateideskriptor und das zugrunde liegende Betriebssystem-Dateihandle. In diesem Fall rufen nicht [_close](close.md) auf den Dateideskriptor.

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
[\_open_osfhandle](open-osfhandle.md)
