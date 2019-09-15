---
title: clearerr
ms.date: 11/04/2016
api_name:
- clearerr
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
- clearerr
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
ms.openlocfilehash: 9fd2f7e7dfcf272e806a887b356418b7555913f5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942949"
---
# <a name="clearerr"></a>clearerr

Setzt den Fehlerindikator für einen Stream zurück. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [clearerr_s](clearerr-s.md).

## <a name="syntax"></a>Syntax

```C
void clearerr(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="remarks"></a>Hinweise

Die **clearerr** -Funktion setzt den Fehler Indikator und den Dateiende-Indikator für den *Stream*zurück. Fehlerindikatoren werden nicht automatisch gelöscht. Sobald der Fehler Indikator für einen angegebenen Stream festgelegt ist, geben Vorgänge in diesem Stream weiterhin einen Fehlerwert zurück, bis **clearerr**, [fseek](fseek-fseeki64.md), **fsetpos**oder [Rewind](rewind.md) aufgerufen wird.

Wenn der Stream **null**ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion **errno** auf **EINVAL** fest und gibt zurück. Weitere Informationen zu **errno** und Fehlercodes finden Sie unter [Errno-Konstanten](../../c-runtime-library/errno-constants.md).

Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [clearerr_s](clearerr-s.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**clearerr**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_clearerr.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      clearerr( stdin );
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      clearerr( stdin );
   }
   else
      printf( "No read error\n" );
}
```

### <a name="input"></a>Eingabe

```Input
n
```

### <a name="output"></a>Ausgabe

```Output
Write error: No error
Will input cause an error? n
No read error
```

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)<br/>
[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
