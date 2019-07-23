---
title: _write
ms.date: 11/04/2016
apiname:
- _write
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
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: 032bf332caee09fbe17d58eeae16ab44b98402d3
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376291"
---
# <a name="write"></a>_write

Schreibt Daten in eine Datei.

## <a name="syntax"></a>Syntax

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor der Datei, in die die Daten geschrieben werden.

*buffer*<br/>
Zu schreibende Daten.

*count*<br/>
Anzahl der Bytes.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung gibt **_write** die Anzahl der geschriebenen Bytes zurück. Wenn der tatsächliche Speicherplatz auf dem Datenträger kleiner ist als die Größe des Puffers, den die Funktion versucht, auf den Datenträger zu schreiben, schlägt **_write** fehl und leert keinen der Inhalte des Puffers auf den Datenträger. Der Rückgabewert-1 gibt einen Fehler an. Wenn ungültige Parameter übergeben werden, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion-1 zurück, und **errno** wird auf einen von drei Werten festgelegt: **EBADF**, d. h. der Dateideskriptor ist ungültig, oder die Datei wird nicht zum Schreiben geöffnet. **ENOSPC**, was bedeutet, dass auf dem Gerät nicht genügend Speicherplatz für den Vorgang vorhanden ist. oder **EINVAL**, d. h., der *Puffer* war ein NULL-Zeiger, oder es wurde eine ungerade *Anzahl* von Bytes an eine Datei im Unicode-Modus übermittelt.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Wenn die Datei im Textmodus geöffnet ist, wird jedes Zeilenvorschub Zeichen durch ein Wagen Rücklauf-Zeilenvorschub-Paar in der Ausgabe ersetzt. Der Ersatz wirkt sich nicht auf den Rückgabewert aus.

Wenn die Datei im Unicode-Übersetzungsmodus geöffnet wird – z. b. Wenn *FD* mit **_open** oder **_sopen** geöffnet wird und ein Modusparameter ist, der **_O_WTEXT**, **_O_U16TEXT**oder **_O_U8TEXT**enthält, oder wenn er mithilfe von geöffnet wird. **fopen** und ein Modusparameter, der **CCS = Unicode**, **CCS = UTF-16LE**oder **CCS = UTF-8**enthält, oder wenn der Modus in einen Unicode-Übersetzungsmodus mithilfe von **_setmode**geändert wird *, wird als* Zeiger auf einen Array von **wchar_t** , das **UTF-16-** Daten enthält. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes zu schreiben, führt zu einem Parametervalidierungsfehler.

## <a name="remarks"></a>Hinweise

Die **_write** -Funktion schreibt *count* -Bytes aus dem *Puffer* in die mit *FD*verknüpfte Datei. Der Schreibvorgang beginnt an der aktuellen Position des Dateizeigers (falls vorhanden) für die betreffende Datei. Wenn die Datei zum Anhängen geöffnet ist, beginnt der Vorgang am aktuellen Dateiende. Nach dem Schreibvorgang wird der Dateizeiger um die Anzahl der geschriebenen Bytes erweitert.

Beim Schreiben in Dateien, die im Textmodus geöffnet wurden, behandelt **_write** ein STRG + Z-Zeichen als logisches Dateiende. Beim Schreiben auf ein Gerät behandelt **_write** ein STRG + Z-Zeichen im Puffer als Ausgabe Abschluss Zeichen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_write**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt__write.c
//
// This program opens a file for output and uses _write to write
// some bytes to the file.

#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <errno.h>
#include <share.h>

char buffer[] = "This is a test of '_write' function";

int main( void )
{
   int         fileHandle = 0;
   unsigned    bytesWritten = 0;

   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )
      return -1;

   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )
   {
      switch(errno)
      {
         case EBADF:
            perror("Bad file descriptor!");
            break;
         case ENOSPC:
            perror("No space left on device!");
            break;
         case EINVAL:
            perror("Invalid parameter: buffer was NULL!");
            break;
         default:
            // An unrelated error occured
            perror("Unexpected error!");
      }
   }
   else
   {
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );
   }
   _close( fileHandle );
}
```

```Output
Wrote 36 bytes to file.
```

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
