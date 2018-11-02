---
title: _setmode
ms.date: 11/04/2016
apiname:
- _setmode
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
- _setmode
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
ms.openlocfilehash: 887936299dce0a13738f9dd891a168785d17c979
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617437"
---
# <a name="setmode"></a>_setmode

Legt den Dateiübersetzungsmodus fest.

## <a name="syntax"></a>Syntax

```C
int _setmode (
   int fd,
   int mode
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor.

*mode*<br/>
Neuer Übersetzungsmodus.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall wird der vorherige Übersetzungsmodus zurückgegeben.

Wenn ungültige Parameter an die Funktion übergeben werden, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md)beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, diese Funktion gibt-1 zurück und legt **Errno** entweder **EBADF**, wodurch einen Ungültiger Dateideskriptor, oder **EINVAL**, kennzeichnet eine ungültige *Modus* Argument.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_setmode** -Funktion legt fest, um *Modus* den Übersetzungsmodus der Datei durch *fd*. Übergeben von **_O_TEXT** als *Modus* legt Text (die übersetzt wird,) Modus. Carriage Return-Line feed (CR-LF) Kombinationen werden in ein einzelnes Zeilenvorschubzeichen bei Eingabe übersetzt. Zeilenvorschubzeichen werden bei der Ausgabe in Kombinationen aus Wagenrücklauf und Zeilenvorschub (CR-LF) übersetzt. Übergeben von **_O_BINARY** legt binären (unübersetzten) Modus, in dem diese Übersetzungen unterdrückt werden.

Sie können auch übergeben **_O_U16TEXT**, **_O_U8TEXT**, oder **_O_WTEXT** Unicode-Modus zu aktivieren, wie im zweiten Beispiel weiter unten in diesem Dokument veranschaulicht. **_setmode** dient normalerweise zum Ändern der Standardmodus für die Übersetzung von **Stdin** und **"stdout"**, aber Sie können auf eine beliebige Datei verwenden. Wenn Sie anwenden **_setmode** aufrufen, um den Dateideskriptor für einen Stream, **_setmode** vor dem Ausführen von Eingabe- oder Vorgänge für den Stream.

> [!CAUTION]
> Wenn Sie Daten in einen Dateistream explizit leeren den Code mithilfe von schreiben [Fflush](fflush.md) vor der Verwendung **_setmode** zum Ändern des websitemodus. Wenn Sie den Code nicht leeren, kann es zu unerwartetem Verhalten kommen. Wenn Sie keine Daten in den Stream geschrieben haben, müssen Sie den Code nicht leeren.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionale Header|
|-------------|---------------------|----------------------|
|**_setmode**|\<io.h>|\<fcntl.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_setmode.c
// This program uses _setmode to change
// stdin from text mode to binary mode.

#include <stdio.h>
#include <fcntl.h>
#include <io.h>

int main( void )
{
   int result;

   // Set "stdin" to have binary mode:
   result = _setmode( _fileno( stdin ), _O_BINARY );
   if( result == -1 )
      perror( "Cannot set mode" );
   else
      printf( "'stdin' successfully changed to binary mode\n" );
}
```

```Output
'stdin' successfully changed to binary mode
```

## <a name="example"></a>Beispiel

```C
// crt_setmodeunicode.c
// This program uses _setmode to change
// stdout to Unicode. Cyrillic and Ideographic
// characters will appear on the console (if
// your console font supports those character sets).

#include <fcntl.h>
#include <io.h>
#include <stdio.h>

int main(void) {
    _setmode(_fileno(stdout), _O_U16TEXT);
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");
    return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_set_fmode](set-fmode.md)<br/>
