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
ms.openlocfilehash: 818051fba093c83d695afcad103865b4114673d0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="chsize"></a>_chsize

Ändert die Größe einer Datei. Es ist eine sicherere Version verfügbar. Informationen dazu finden Sie unter [_chsize_s](chsize-s.md).

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

**_chsize** gibt den Wert 0 zurück, wenn die Dateigröße erfolgreich geändert wurde. Ein Rückgabewert von – 1 zeigt einen Fehler: **Errno** festgelegt ist, um **EACCES** , wenn die angegebene Datei schreibgeschützt ist oder die angegebene Datei ist gesperrt, Zugriff, zu **EBADF** Wenn die Sicherheitsbeschreibung ist ungültig, **ENOSPC** Wenn kein auf dem Gerät Speicherplatz oder **EINVAL** Wenn *Größe* ist kleiner als 0 (null).

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_chsize** Funktion erweitert oder verkürzt die zugeordnete Datei *fd* auf die Länge, angegeben durch *Größe*. Die Datei muss in einem Modus geöffnet sein, der Schreiben zulässt. Wenn die Datei erweitert wird, werden NULL-Zeichen ('\0') angefügt. Wenn die Datei abgeschnitten wird, gehen alle Daten vom Ende der gekürzten Datei bis zur ursprünglichen Länge der Datei verloren.

Diese Funktion überprüft ihre Parameter. Wenn *Größe* ist kleiner als 0 (null) oder *fd* ein fehlerhaften Dateideskriptor wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_chsize**|\<io.h>|\<errno.h>|

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
[_close](close.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
