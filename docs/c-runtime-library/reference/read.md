---
title: _read
ms.date: 11/04/2016
apiname:
- _read
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
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: 8c43cbbc2681433bda02038ae73a827fad904835
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658442"
---
# <a name="read"></a>_read

Liest Daten aus einer Datei.

## <a name="syntax"></a>Syntax

```C
int _read(
   int fd,
   void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor, der auf die geöffnete Datei verweist.

*buffer*<br/>
Speicherort für Daten.

*count*<br/>
Die maximale Anzahl von Bytes.

## <a name="return-value"></a>Rückgabewert

**_read** gibt die Anzahl der gelesenen Bytes an, der möglicherweise kleiner als *Anzahl* Wenn weniger als *Anzahl* Bytes in der Datei übrig, oder wenn die Datei im Textmodus geöffnet wurde, in diesem Fall wird jede Wagenrücklauf Return-Zeilenvorschub-Paar "\r\n" wird durch ein einzelnes Zeilenvorschubzeichen '\n' ersetzt. Nur das einzelne Zeilenvorschubzeichen wird im Rückgabewert gezählt. Der Ersatz hat keine Auswirkung auf den Rückgabezeiger.

Wenn die Funktion versucht, am Ende der Datei zu lesen, wird 0 zurückgegeben. Wenn *fd* ist nicht gültig ist, die Datei ist nicht zum Lesen geöffnet, oder die Datei ist gesperrt, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktion gibt-1 zurück und legt **Errno** zu **EBADF**.

Wenn *buffer* **NULL** ist, wird der ungültige Parameterhandler aufgerufen. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, gibt die Funktion-1 zurück und **Errno** nastaven NA hodnotu **EINVAL**.

Weitere Informationen zu diesem und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_read** -Funktion liest maximal *Anzahl* Bytes in *Puffer* aus der Datei zugeordneten *fd*. Der Lesevorgang beginnt an der aktuellen Position des Dateizeigers für die betreffende Datei. Nach dem Lesevorgang zeigt der Dateizeiger auf das nächste ungelesene Zeichen.

Wenn die Datei im Textmodus geöffnet wurde, der Lesevorgang beendet, wenn **_read** findet ein STRG + Z-Zeichen, das als Dateiende-Indikator behandelt wird. Verwenden Sie [_lseek](lseek-lseeki64.md), um den Dateiende-Indikator zu löschen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_read**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_read.c
/* This program opens a file named crt_read.txt
* and tries to read 60,000 bytes from
* that file using _read. It then displays the
* actual number of bytes read.
*/

#include <fcntl.h>      /* Needed only for _O_RDWR definition */
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

char buffer[60000];

int main( void )
{
   int fh;
   unsigned int nbytes = 60000, bytesread;

   /* Open file for input: */
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
   {
      perror( "open failed on input file" );
      exit( 1 );
   }

   /* Read in input: */
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )
      perror( "Problem reading file" );
   else
      printf( "Read %u bytes from file\n", bytesread );

   _close( fh );
}
```

### <a name="input-crtreadtxt"></a>Eingabe: crt_read.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Output

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_write](write.md)<br/>
