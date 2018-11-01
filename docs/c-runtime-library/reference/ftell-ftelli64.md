---
title: ftell, _ftelli64
ms.date: 11/04/2016
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: cc76ad0776ae82637b95d32cdc6254d3c40da5b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660524"
---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64

Ruft die aktuelle Position eines Dateizeigers ab

## <a name="syntax"></a>Syntax

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Ziel **Datei** Struktur.

## <a name="return-value"></a>Rückgabewert

**Ftell** und **_ftelli64** die aktuelle Dateiposition zurück. Der Rückgabewert von **Ftell** und **_ftelli64** das physische Byteoffset für im Textmodus geöffneten Streams u. u. nicht wiedergegeben werden, weil im Textmodus Carriage Return-Zeilenvorschub-Übersetzung verursacht. Verwendung **Ftell** mit [Fseek](fseek-fseeki64.md) oder **_ftelli64** mit [_fseeki64](fseek-fseeki64.md) auf Dateispeicherorte ordnungsgemäß zurückgegeben. Bei einem Fehler **Ftell** und **_ftelli64** der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, diese Funktionen zurück,-1 L und legen **Errno** auf eine der beiden Konstanten, die in ERRNO definiert. H. Die **EBADF** -Konstante bedeutet, dass die *Stream* Argument ein gültiger dateizeigerwert ist oder nicht auf eine geöffnete Datei verweist. **EINVAL** bedeutet, dass eine ungültige *Stream* Argument wurde an die Funktion übergeben. Auf Geräten, die über keine Suchfunktion verfügen (z.B. Terminals oder Drucker) oder wenn *Stream* verweist nicht auf eine geöffnete Datei, ist der Rückgabewert nicht definiert.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Ftell** und **_ftelli64** Funktionen Abrufen die aktuelle Position des Dateizeigers (sofern vorhanden) zugeordneten *Stream*. Die Position wird als ein Offset relativ zum Anfang des Streams ausgedrückt.

Beachten Sie, dass wenn eine Datei zum Anfügen von Daten geöffnet wird, die aktuelle Dateiposition vom letzten E/A-Vorgang nicht dadurch bestimmt wird, wo der nächste Schreibvorgang erfolgt. Wenn eine Datei für einen Anfügevorgang geöffnet wird und der letzte Vorgang ein Lesevorgang war, ist die Dateiposition der Punkt, an dem der nächste Lesevorgang gestartet wird, aber nicht der nächste Schreibvorgang. (Wenn eine Datei für einen Anfügevorgang geöffnet wird, wird die Dateiposition vor einem Schreibvorgang an das Ende der Datei verschoben.) Wenn noch kein E/A-Vorgang für eine zum Anhängen geöffnete Datei stattgefunden hat, ist die Dateiposition der Anfang der Datei.

Im Textmodus wird STRG+Z in der Eingabe als Dateiendezeichen interpretiert. In den Dateien geöffnet zum Lesen/Schreiben **Fopen** und alle verknüpfte Routinen STRG + z am Ende der Datei überprüfen und ggf. zu entfernen. Dies geschieht, da die Verwendung **Ftell** und [Fseek](fseek-fseeki64.md) oder **_ftelli64** und [_fseeki64](fseek-fseeki64.md), zum Navigieren innerhalb einer Datei, die mit endet STRG + Z möglicherweise **Ftell** oder **_ftelli64** am Ende der Datei nicht ordnungsgemäß verhält.

Diese Funktion sperrt den aufrufenden Thread während der Ausführung und ist threadsicher. Eine nicht sperrende Version finden Sie unter **_ftell_nolock**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|Optionale Header|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
