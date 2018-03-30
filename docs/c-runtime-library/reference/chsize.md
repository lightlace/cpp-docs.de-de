---
title: _chsize | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _chsize
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
- _chsize
dev_langs:
- C++
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cec2d058b356cbb7624ee6dd0bbecdfb55c64813
ms.sourcegitcommit: cdd4808dcb274bbb29618286df4d1d4acd35b9bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2018
---
# <a name="chsize"></a>_chsize

Ändert die Größe einer Datei. Es ist eine sicherere Version verfügbar. Informationen dazu finden Sie unter [_chsize_s](../../c-runtime-library/reference/chsize-s.md).

## <a name="syntax"></a>Syntax

```C
int _chsize(
   int fd,
   long size
);
```

### <a name="parameters"></a>Parameter
*fd*<br/>
Dateideskriptor, der auf eine geöffnete Datei verweist.

*size*<br/>
Neue Länge der Datei in Bytes.

## <a name="return-value"></a>Rückgabewert

_chsize` returns the value 0 if the file size is successfully changed. A return value of -1 indicates an error: `errno` is set to `EACCES` if the specified file is read-only or the specified file is locked against access, to `EBADF` if the descriptor is invalid, `ENOSPC` if no space is left on the device, or `EINVAL` if `size` is less than zero.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die `_chsize`-Funktion erweitert oder verkürzt die mit `fd` verknüpfte Datei auf die von `size` angegebene Länge. Die Datei muss in einem Modus geöffnet sein, der Schreiben zulässt. Wenn die Datei erweitert wird, werden NULL-Zeichen ('\0') angefügt. Wenn die Datei abgeschnitten wird, gehen alle Daten vom Ende der gekürzten Datei bis zur ursprünglichen Länge der Datei verloren.

Diese Funktion überprüft ihre Parameter. Wenn `size` kleiner als null ist oder `fd` ein fehlerhafter Dateideskriptor ist, wird – wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben – der Handler für ungültige Parameter aufgerufen.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|`_chsize`|\<io.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_chsize.c
// This program uses _filelength to report the size
// of a file before and after modifying it with _chsize.

#include <io.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <share.h>

int main( void )
{
   int fh, result;
   unsigned int nbytes = BUFSIZ;

   // Open a file
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,
                 _S_IREAD | _S_IWRITE ) == 0 )
   {
      printf( "File length before: %ld\n", _filelength( fh ) );
      if( ( result = _chsize( fh, 329678 ) ) == 0 )
         printf( "Size successfully changed\n" );
      else
         printf( "Problem in changing the size\n" );
      printf( "File length after:  %ld\n", _filelength( fh ) );
      _close( fh );
   }
}
```

```Output
File length before: 0
Size successfully changed
File length after:  329678
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_close](../../c-runtime-library/reference/close.md)<br/>
[_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_open, _wopen](../../c-runtime-library/reference/open-wopen.md)<br/>
