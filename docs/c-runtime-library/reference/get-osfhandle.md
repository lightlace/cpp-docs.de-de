---
title: _get_osfhandle
ms.date: 05/29/2018
api_name:
- _get_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: 65060689e0a7fc72b67da8fc3bf7ce0af75fd645
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955772"
---
# <a name="_get_osfhandle"></a>_get_osfhandle

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

Gibt ein Betriebssystem-Datei Handle zurück, wenn *FD* gültig ist. Ansonsten wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird **INVALID_HANDLE_VALUE** (-1) zurückgegeben. Außerdem wird **errno** auf **EBADF**festgelegt, was auf ein ungültiges Datei Handle hinweist. Um eine Warnung zu vermeiden, wenn das Ergebnis als Win32-Datei Handle verwendet wird, wandeln Sie es in einen **Handles** -Typ um.

> [!NOTE]
> Wenn **stdin**, **stdout**und **stderr** keinem Stream zugeordnet sind (z. b. in einer Windows-Anwendung ohne Konsolenfenster), werden die Datei deskriptorwerte für diese Streams von [_fileno](fileno.md) als spezieller Wert-2 zurückgegeben. Wenn Sie einen 0, 1 oder 2 als Dateideskriptor-Parameter anstelle des Ergebnisses eines **_fileno**-Aufrufes verwenden, gibt **_get_osfhandle** ebenfalls den besonderen Wert-2 zurück, wenn der Dateideskriptor keinem Stream zugeordnet ist, und legt **errno**fest. Dies ist jedoch kein gültiger Datei Handle-Wert, und nachfolgende Aufrufe, bei denen versucht wird, diese zu verwenden, schlagen wahrscheinlich fehl.

Weitere Informationen zu **EBADF** und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Um eine Datei zu schließen, deren Betriebssystem-Datei Handle von **_get_osfhandle**abgerufen wird, nennen Sie [_close](close.md) im Dateideskriptor *FD*. " **CloseHandle** " niemals für den Rückgabewert dieser Funktion aufgerufen werden. Das zugrunde liegende Betriebssystem-Datei Handle befindet sich im Besitz des *FD* -Datei Deskriptors und wird geschlossen, wenn [_close](close.md) für *FD*aufgerufen wird. Wenn der Dateideskriptor einem `FILE *` Stream gehört, schließt der Aufruf von [fclose](fclose-fcloseall.md) für diesen `FILE *` Stream sowohl den Dateideskriptor als auch das zugrunde liegende Betriebssystem-Datei handle. In diesem Fall muss [_close](close.md) nicht für den Dateideskriptor aufgerufen werden.

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
