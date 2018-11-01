---
title: _chsize_s
ms.date: 11/04/2016
apiname:
- _chsize_s
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
- chsize_s
- _chsize_s
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
ms.openlocfilehash: a56efe826d43c80dc2cdee295e58872e7dd3c9ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597599"
---
# <a name="chsizes"></a>_chsize_s

Ändert die Größe einer Datei. Dies ist eine sicherere Version von [_chsize](chsize.md), wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

## <a name="syntax"></a>Syntax

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor, der auf eine geöffnete Datei verweist.

*size*<br/>
Neue Länge der Datei in Bytes.

## <a name="return-value"></a>Rückgabewert

**_chsize_s** gibt den Wert 0 zurück, wenn die Dateigröße erfolgreich geändert wurde. Ein Rückgabewert ungleich Null gibt einen Fehler: der Rückgabewert ist **EACCES** , wenn die angegebene Datei für den Zugriff gesperrt ist **EBADF** , wenn die angegebene Datei schreibgeschützt ist oder des Deskriptors ungültig ist, **ENOSPC** , wenn kein Speicherplatz mehr auf dem Gerät vorhanden ist oder **EINVAL** Wenn Größe ist kleiner als 0 (null). **Errno** auf den gleichen Wert festgelegt ist.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_chsize_s** -Funktion erweitert oder verkürzt die zugeordnete Datei *fd* der vom angegebenen Länge *Größe*. Die Datei muss in einem Modus geöffnet sein, der Schreiben zulässt. Wenn die Datei erweitert wird, werden NULL-Zeichen ('\0') angefügt. Wenn die Datei abgeschnitten wird, gehen alle Daten vom Ende der gekürzten Datei bis zur ursprünglichen Länge der Datei verloren.

**_chsize_s** ist eine 64-Bit-Ganzzahl als die Dateigröße, und aus diesem Grund können Dateien handhaben, größer als 4 GB. **_chsize** ist auf 32-Bit-Dateigrößen.

Diese Funktion überprüft ihre Parameter. Wenn *fd* ist ein gültiger Dateideskriptor oder die Größe ist kleiner als 0 (null), wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
