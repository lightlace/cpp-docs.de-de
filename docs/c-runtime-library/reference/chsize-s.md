---
title: _chsize_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8867761f644e1367c3ab1101a9a5860b9cfc9c33
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

**_chsize_s** gibt den Wert 0 zurück, wenn die Dateigröße erfolgreich geändert wurde. Ein Wert ungleich Null zeigt einen Fehler: der Rückgabewert ist **EACCES** Wenn für den Zugriff auf die angegebene Datei gesperrt ist **EBADF** , wenn die angegebene Datei schreibgeschützt ist oder die Beschreibung ungültig ist, **ENOSPC** Wenn kein auf dem Gerät Speicherplatz oder **EINVAL** Wenn Größe ist kleiner als 0 (null). **Errno** auf denselben Wert festgelegt ist.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_chsize_s** Funktion erweitert oder verkürzt die zugeordnete Datei *fd* auf die Länge, angegeben durch *Größe*. Die Datei muss in einem Modus geöffnet sein, der Schreiben zulässt. Wenn die Datei erweitert wird, werden NULL-Zeichen ('\0') angefügt. Wenn die Datei abgeschnitten wird, gehen alle Daten vom Ende der gekürzten Datei bis zur ursprünglichen Länge der Datei verloren.

**_chsize_s** ist eine 64-Bit-Ganzzahl als die Dateigröße, und daher Dateigrößen, die größer als 4 GB verarbeiten kann. **_chsize** ist auf 32-Bit-Dateigrößen beschränkt.

Diese Funktion überprüft ihre Parameter. Wenn *fd* ist eine gültige Dateideskriptor oder Größe ist kleiner als 0 (null), wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
