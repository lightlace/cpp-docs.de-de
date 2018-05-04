---
title: _locking | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _locking
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
- _locking
dev_langs:
- C++
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1666f631d9bceccb8925b2002b797753e024ab9d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="locking"></a>_locking

Sperrt oder entsperrt Bytes einer Datei.

## <a name="syntax"></a>Syntax

```C
int _locking(
   int fd,
   int mode,
   long nbytes
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor.

*mode*<br/>
Die auszuführende Sperraktion

*nbytes*<br/>
Die Anzahl der zu sperrenden Bytes.

## <a name="return-value"></a>Rückgabewert

**_Locking** gibt bei Erfolg 0 zurück. Ein Rückgabewert-1 gibt Fehler auftritt, in diesem Fall an [Errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) auf einen der folgenden Werte festgelegt.

|errno-Wert|Bedingung|
|-|-|
**EACCES**|Sperrverletzung (Datei bereits gesperrt oder entsperrt).
**EBADF**|Ungültiger Dateideskriptor.
**EDEADLOCK**|Sperrverletzung. Zurückgegeben, wenn die **_LK_LOCK** oder **_LK_RLCK** Flag angegeben wird und die Datei kann nicht nach 10 Versuchen nicht gesperrt werden.
**EINVAL**|Ein ungültiges Argument wurde angegeben, um **_locking**.

Wenn der Fehler aufgrund eines ungültigen Parameters entstanden ist, wie z.B. ein ungültiger Dateideskriptor, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.

## <a name="remarks"></a>Hinweise

Die **_locking** Funktion sperrt oder entsperrt *Anzahl_Byte* Bytes der Datei gemäß *fd*. Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Alle Sperr- oder Entsperraktionen beginnen an der aktuellen Position des Dateizeigers und laufen für die nächsten *nbytes*-Bytes ab. Es ist möglich, Bytes nach dem Ende der Datei zu sperren.

Der *Modus* muss eine der folgenden Manifestkonstanten sein, die in „Locking.h“ definiert sind.

|*Modus* Wert|Effekt|
|-|-|
**_LK_LOCK**|Sperrt die angegebenen Bytes. Wenn die Bytes nicht gesperrt werden können, führt das Programm nach 1 Sekunde sofort einen neuen Versuch durch. Wenn nach 10 Versuchen die Bytes nicht gesperrt werden können, gibt die Konstante einen Fehler zurück.
**_LK_NBLCK**|Sperrt die angegebenen Bytes. Wenn die Bytes nicht gesperrt werden können, gibt die Konstante einen Fehler zurück.
**_LK_NBRLCK**|Identisch mit **_LK_NBLCK**.
**_LK_RLCK**|Identisch mit **_LK_LOCK**.
**_LK_UNLCK**|Entsperrt die angegebenen Bytes, die zuvor gesperrt sein mussten.

Mehrere Bereiche einer Datei, die sich nicht überschneiden, können gesperrt werden. Ein Bereich, der entsperrt wird, muss zuvor gesperrt worden sein. **_Locking** nicht zusammenführen, angrenzende Regionen ist; Wenn zwei gesperrte Bereiche nebeneinander angeordnet sind, jede Region muss entsperrt werden separat. Bereichen sollten nur über einen kurzen Zeitraum gesperrt sein und sollten entsperrt werden, bevor eine Datei geschlossen oder das Programm beendet wird.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_locking**|\<io.h> und \<sys/locking.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_locking.c
/* This program opens a file with sharing. It locks
* some bytes before reading them, then unlocks them. Note that the
* program works correctly only if the file exists.
*/

#include <sys/types.h>
#include <sys/stat.h>
#include <sys/locking.h>
#include <share.h>
#include <fcntl.h>
#include <stdio.h>
#include <stdlib.h>
#include <io.h>

int main( void )
{
   int  fh, numread;
   char buffer[40];

   /* Quit if can't open file or system doesn't
    * support sharing.
    */
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,
                          _S_IREAD | _S_IWRITE );
   printf( "%d %d\n", err, fh );
   if( err != 0 )
      exit( 1 );

   /* Lock some bytes and read them. Then unlock. */
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )
   {
      long lseek_ret;
      printf( "No one can change these bytes while I'm reading them\n" );
      numread = _read( fh, buffer, 30 );
      buffer[30] = '\0';
      printf( "%d bytes read: %.30s\n", numread, buffer );
      lseek_ret = _lseek( fh, 0L, SEEK_SET );
      _locking( fh, LK_UNLCK, 30L );
      printf( "Now I'm done. Do what you will with them\n" );
   }
   else
      perror( "Locking failed\n" );

   _close( fh );
}
```

### <a name="input-crtlockingtxt"></a>Eingabe: crt_locking.txt

```Input
The first thirty bytes of this file will be locked.
```

## <a name="sample-output"></a>Beispielausgabe

```Output
No one can change these bytes while I'm reading them
30 bytes read: The first thirty bytes of this
Now I'm done. Do what you will with them
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
