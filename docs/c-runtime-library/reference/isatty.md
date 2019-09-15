---
title: _isatty
ms.date: 11/04/2016
api_name:
- _isatty
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _isatty
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
ms.openlocfilehash: 2d2ba2fdfeb1c8bffe47b0953f0629746d2eb599
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954555"
---
# <a name="_isatty"></a>_isatty

Bestimmt, ob ein Dateideskriptor einem Zeichengerät zugeordnet ist.

## <a name="syntax"></a>Syntax

```C
int _isatty( int fd );
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor, der auf das zu testende Gerät verweist.

## <a name="return-value"></a>Rückgabewert

**_isatty** gibt einen Wert ungleich 0 (null) zurück, wenn der Deskriptor einem Zeichengerät zugeordnet ist. Andernfalls gibt **_isatty** 0 zurück.

## <a name="remarks"></a>Hinweise

Die **_isatty** -Funktion bestimmt, ob *FD* einem Zeichengerät (Terminal, Konsole, Drucker oder serieller Anschluss) zugeordnet ist.

Diese Funktion überprüft den *FD* -Parameter. Wenn *FD* ein fehlerhafter Dateizeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion 0 zurück und legt **errno** auf **EBADF**fest.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_isatty**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_isatty.c
/* This program checks to see whether
* stdout has been redirected to a file.
*/

#include <stdio.h>
#include <io.h>

int main( void )
{
   if( _isatty( _fileno( stdout ) ) )
      printf( "stdout has not been redirected to a file\n" );
   else
      printf( "stdout has been redirected to a file\n");
}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
stdout has not been redirected to a file
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
