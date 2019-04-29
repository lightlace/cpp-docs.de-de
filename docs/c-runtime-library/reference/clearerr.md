---
title: clearerr
ms.date: 11/04/2016
apiname:
- clearerr
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
- clearerr
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
ms.openlocfilehash: c282a577bb7496f899f18abeac857c08388d12f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340553"
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

Die **Clearerr** Funktion setzt den Fehlerindikator und den Dateiende-Indikator für *Stream*. Fehlerindikatoren werden nicht automatisch gelöscht; Sobald der Fehlerindikator für einen bestimmten Stream festgelegt wurde, Operationen in diesem Stream weiterhin einen Fehlerwert bis zurück **Clearerr**, [Fseek](fseek-fseeki64.md), **Fsetpos**, oder [rewind](rewind.md) aufgerufen wird.

Wenn *Stream* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und zurückgibt. Weitere Informationen zu **Errno** und Fehlercodes finden Sie unter [Errno-Konstanten](../../c-runtime-library/errno-constants.md).

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

### <a name="output"></a>Output

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
