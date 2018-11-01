---
title: fseek, _fseeki64
ms.date: 11/04/2016
apiname:
- _fseeki64
- fseek
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
- fseek
- _fseeki64
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
ms.openlocfilehash: 15ff6e4a70069845369acdc3ffd153c48f228201
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447540"
---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64

Verschiebt den Dateizeiger in einen angegebenen Speicherort

## <a name="syntax"></a>Syntax

```C
int fseek(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

*offset*<br/>
Anzahl von Bytes von *origin*.

*origin*<br/>
Ursprüngliche Position.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **Fseek** und **_fseeki64** gibt 0 zurück. Andernfalls gibt es einen Wert ungleich 0 (null) zurück. Auf Geräten, die Suchvorgänge nicht unterstützen, ist der Rückgabewert nicht definiert. Wenn *Stream* ein null-Zeiger ist oder wenn *Ursprung* ist keiner der zulässigen Werte, die unten beschriebenen **Fseek** und **_fseeki64** rufen Sie die ungültigen parameterhandler, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL** und geben-1 zurück.

## <a name="remarks"></a>Hinweise

Die **Fseek** und **_fseeki64** functions verschiebt der Dateizeiger (sofern vorhanden) zugeordneten *Stream* an einem neuen Speicherort, der *Offset* Bytes von *Ursprung*. Der nächste Vorgang im Stream tritt am neuen Speicherort auf. Für einen updatebereiten Stream kann der nächste Vorgang ein Lese- oder Schreibvorgang sein. Das Argument *Ursprung* muss eine der folgenden Konstanten, definiert in STDIO sein. H:

|Origin-Wert|Bedeutung|
|-|-|
**SEEK_CUR**|Aktuelle Position des Dateizeigers
**SEEK_END**|Ende der Datei
**SEEK_SET**|Anfang der Datei

Sie können **Fseek** und **_fseeki64** um den Zeiger an einer beliebigen Stelle in einer Datei zu verschieben. Der Zeiger kann auch nach dem Ende der Datei positioniert werden. **Fseek** und **_fseeki64** löscht den Dateiende-Indikator und negieren die Auswirkung aller vorherigen [Ungetc](ungetc-ungetwc.md) Laufzeitaufrufe *Stream*.

Wenn eine Datei zum Anfügen von Daten geöffnet wird, wird die aktuelle Dateiposition vom letzten E/A-Vorgang nicht dadurch bestimmt, wo der nächste Schreibvorgang erfolgt. Wenn noch kein E/A-Vorgang für eine zum Anhängen geöffnete Datei stattgefunden hat, ist die Dateiposition der Anfang der Datei.

Für im Textmodus geöffneten Streams **Fseek** und **_fseeki64** nur begrenzt verwendet, da Carriage Return-zeilenvorschubübersetzungen dazu **Fseek** und **_ fseeki64** zu unerwarteten Ergebnissen führen. Die einzige **Fseek** und **_fseeki64** sind Vorgänge, die garantiert auf im Textmodus geöffneten Streams funktionieren:

- Suchen mit einem Offset von 0 hinsichtlich der ursprünglichen Werte

- Ab dem Anfang der Datei mit einem Offsetwert Suchen von einem Aufruf zurückgegebenen [Ftell](ftell-ftelli64.md) Verwendung **Fseek** oder [_ftelli64](ftell-ftelli64.md) Verwendung **_fseeki64**.

Im Textmodus wird STRG+Z als ein Dateiendezeichen in der Eingabe interpretiert. In den Dateien geöffnet zum Lesen/Schreiben [Fopen](fopen-wfopen.md) und alle verknüpfte Routinen STRG + z am Ende der Datei überprüfen und ggf. zu entfernen. Dies geschieht, da die Verwendung **Fseek** und [Ftell](ftell-ftelli64.md) oder **_fseeki64** und [_ftelli64](ftell-ftelli64.md), zum Navigieren innerhalb einer Datei, die mit endet STRG + Z möglicherweise **Fseek** oder **_fseeki64** am Ende der Datei nicht ordnungsgemäß verhält.

Wenn CRT eine Datei öffnet, die mit einer Bytereihenfolge-Marke (Byte Order Mark, BOM) beginnt, wird der Dateizeiger nach der BOM positioniert (d.h. am Anfang des tatsächlichen Dateiinhalts). Sie ggf. **Fseek** verwenden, um den Anfang der Datei, [Ftell](ftell-ftelli64.md) auf die ursprüngliche Position abzurufen und **Fseek** , anstatt auf position 0.

Diese Funktion sperrt alle anderen Threads während der Ausführung und ist daher threadsicher. Eine nicht sperrende Version finden Sie unter [_fseek_nolock, _fseeki64_nolock](fseek-nolock-fseeki64-nolock.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fseek**|\<stdio.h>|
|**_fseeki64**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fseek.c
// This program opens the file FSEEK.OUT and
// moves the pointer to the file's beginning.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[81];
   int  result;

   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )
   {
      printf( "The file fseek.out was not opened\n" );
      return -1;
   }
   fprintf( stream, "The fseek begins here: "
                    "This is the file 'fseek.out'.\n" );
   result = fseek( stream, 23L, SEEK_SET);
   if( result )
      perror( "Fseek failed" );
   else
   {
      printf( "File pointer is set to middle of first line.\n" );
      fgets( line, 80, stream );
      printf( "%s", line );
    }
   fclose( stream );
}
```

```Output
File pointer is set to middle of first line.
This is the file 'fseek.out'.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
