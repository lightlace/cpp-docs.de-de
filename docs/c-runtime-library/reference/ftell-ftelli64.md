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
ms.openlocfilehash: f9548d4684bd2df734be2b0b703f98d8c7982884
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376123"
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

*stream*<br/>
Ziel **Datei** Struktur.

## <a name="return-value"></a>Rückgabewert

" **f** " und " **_ftelli64** " geben die aktuelle Dateiposition zurück. Der von " **f** " und " **_ftelli64** " zurückgegebene Wert spiegelt möglicherweise nicht den physischen Byte Offset für Streams wider, die im Textmodus geöffnet wurden, da der Textmodus eine Wagen Rücklauf-Zeilenvorschub Übersetzung Verwenden Sie **ftell** mit [fseek](fseek-fseeki64.md) oder **_ftelli64** mit [_fseeki64](fseek-fseeki64.md) , um ordnungsgemäß zu den Dateispeicher Orten zurückzukehren. Bei Error rufen **ftell** und **_ftelli64** den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "-1L" zurück und setzen " **errno** " auf eine von zwei Konstanten, die in "errno" definiert sind. Micha. Die **EBADF** -Konstante bedeutet, dass das *Stream* -Argument kein gültiger Dateizeiger Wert ist oder nicht auf eine geöffnete Datei verweist. **EINVAL** bedeutet, dass ein ungültiges *Stream* -Argument an die Funktion übermittelt wurde. Auf Geräten, die nicht suchen können (z. b. Terminals und Drucker), oder wenn der *Stream* nicht auf eine geöffnete Datei verweist, ist der Rückgabewert nicht definiert.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **ftell** -Funktion und die **_ftelli64** -Funktion rufen die aktuelle Position des Dateizeigers (sofern vorhanden) ab, der dem *Stream*zugeordnet ist. Die Position wird als ein Offset relativ zum Anfang des Streams ausgedrückt.

Beachten Sie, dass wenn eine Datei zum Anfügen von Daten geöffnet wird, die aktuelle Dateiposition vom letzten E/A-Vorgang nicht dadurch bestimmt wird, wo der nächste Schreibvorgang erfolgt. Wenn eine Datei für einen Anfügevorgang geöffnet wird und der letzte Vorgang ein Lesevorgang war, ist die Dateiposition der Punkt, an dem der nächste Lesevorgang gestartet wird, aber nicht der nächste Schreibvorgang. (Wenn eine Datei für einen Anfügevorgang geöffnet wird, wird die Dateiposition vor einem Schreibvorgang an das Ende der Datei verschoben.) Wenn noch kein E/A-Vorgang für eine zum Anhängen geöffnete Datei stattgefunden hat, ist die Dateiposition der Anfang der Datei.

Im Textmodus wird STRG+Z in der Eingabe als Dateiendezeichen interpretiert. In **Dateien, die** für Lese-/Schreibvorgänge geöffnet sind, überprüfen Sie, ob die Datei mit dem Namen STRG + Z am Ende der Datei ist, und entfernen Sie Sie, wenn möglich. Dies geschieht, da die Kombination von **ftell** und [fseek](fseek-fseeki64.md) bzw. **_ftelli64** und [_fseeki64](fseek-fseeki64.md)zum Verschieben innerhalb einer Datei, die mit STRG + Z endet, dazu führen kann, dass sich **ftell** oder **_ftelli64** nicht ordnungsgemäß am Ende der Datei.

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
