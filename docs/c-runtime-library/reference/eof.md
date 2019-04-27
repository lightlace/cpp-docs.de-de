---
title: _eof
ms.date: 11/04/2016
apiname:
- _eof
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
- _eof
helpviewer_keywords:
- eof function
- end of file, testing for
- _eof function
- files [C++], end of
- testing, for end-of-file
- end of file
ms.assetid: 265703f4-d07e-4005-abf3-b1d0cdd9e0b0
ms.openlocfilehash: 1da849c3721d4d83ff0b3166bc18f95728ebf124
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288135"
---
# <a name="eof"></a>_eof

Tests für das Ende der Datei (EOF).

## <a name="syntax"></a>Syntax

```C
int _eof(
   int fd
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor, der auf die geöffnete Datei verweist.

## <a name="return-value"></a>Rückgabewert

**_eof** gibt 1 zurück, wenn die aktuelle Position Ende der Datei, oder 0 ist, ist dies nicht. Der Rückgabewert 1 gibt an, ein Fehler; In diesem Fall den Handler für ungültige Parameter aufgerufen wird, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EBADF**, wodurch einen Ungültiger Dateideskriptor.

## <a name="remarks"></a>Hinweise

Die **_eof** Funktion bestimmt, ob das Ende der Datei zugeordnet *fd* wurde erreicht.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|Optionaler Header|
|--------------|---------------------|---------------------|
|**_eof**|\<io.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_eof.c
// This program reads data from a file
// ten bytes at a time until the end of the
// file is reached or an error is encountered.
//
#include <io.h>
#include <fcntl.h>
#include <stdio.h>
#include <stdlib.h>
#include <share.h>

int main( void )
{
   int  fh, count, total = 0;
   char buf[10];
   if( _sopen_s( &fh, "crt_eof.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
   {
        perror( "Open failed");
        exit( 1 );
   }
   // Cycle until end of file reached:
   while( !_eof( fh ) )
   {
      // Attempt to read in 10 bytes:
      if( (count = _read( fh, buf, 10 )) == -1 )
      {
         perror( "Read error" );
         break;
      }
      // Total actual bytes read
      total += count;
   }
   printf( "Number of bytes read = %d\n", total );
   _close( fh );
}
```

### <a name="input-crteoftxt"></a>Eingabe: crt_eof.txt

```Input
This file contains some text.
```

### <a name="output"></a>Output

```Output
Number of bytes read = 29
```

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)<br/>
[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
