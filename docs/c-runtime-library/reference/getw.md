---
title: _getw
ms.date: 11/04/2016
apiname:
- _getw
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
- _getw
helpviewer_keywords:
- _getw function
- integers, getting from streams
- getw function
ms.assetid: ef75facc-b84e-470f-9f5f-8746c90822a0
ms.openlocfilehash: 615d3ac9bdc73ad200368eaeabf7c84951bc91ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487606"
---
# <a name="getw"></a>_getw

Ruft eine Ganzzahl aus einem Stream ab.

## <a name="syntax"></a>Syntax

```C
int _getw(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**_getw** gibt den ganzzahligen Wert zu lesen. Der Rückgabewert **EOF** gibt an, einen Fehler oder ein Dateiende. Aber da die **EOF** Wert ist auch ein legitimer Ganzzahlwert, verwenden Sie **Feof** oder **Ferror** um eine End-of-File oder eine fehlerbedingung zu überprüfen. Wenn *Stream* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **EOF**.

## <a name="remarks"></a>Hinweise

Die **_getw** Funktion liest den nächsten Binärwert des Typs **Int** aus der Datei zugeordneten *Stream* und erhöht den zugeordneten Dateizeiger (sofern vorhanden), um zu zeigen auf das nächste ungelesene Zeichen. **_getw** allen speziellen elementausrichtungen im Stream nicht vorausgesetzt. Probleme beim Portieren können beim Auftreten **_getw** da die Größe der **Int** Typ und die Anordnung der Bytes in der **Int** Typ über Systeme hinweg zu unterscheiden.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_getw**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_getw.c
// This program uses _getw to read a word
// from a stream, then performs an error check.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   int i;

   if( fopen_s( &stream, "crt_getw.txt", "rb" ) )
      printf( "Couldn't open file\n" );
   else
   {
      // Read a word from the stream:
      i = _getw( stream );

      // If there is an error...
      if( ferror( stream ) )
      {
         printf( "_getw failed\n" );
         clearerr_s( stream );
      }
      else
         printf( "First data word in file: 0x%.4x\n", i );
      fclose( stream );
   }
}
```

### <a name="input-crtgetwtxt"></a>Eingabe: crt_getw.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Output

```Output
First data word in file: 0x656e694c
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_putw](putw.md)<br/>
