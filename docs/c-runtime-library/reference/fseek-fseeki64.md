---
title: fseek, _fseeki64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- fseek
- _fseeki64
dev_langs:
- C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a327bf196da71f47262c957e7fe6a8352971c36d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

Im Erfolgsfall **Fseek** und **_fseeki64** gibt 0 zurück. Andernfalls gibt es einen Wert ungleich 0 (null) zurück. Auf Geräten, die Suchvorgänge nicht unterstützen, ist der Rückgabewert nicht definiert. Wenn *Stream* ein null-Zeiger ist oder wenn *Ursprung* ist kein zulässiger Werte, die unten beschriebenen **Fseek** und **_fseeki64** den ungültigen aufrufen parameterhandler, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** und geben-1 zurück.

## <a name="remarks"></a>Hinweise

Die **Fseek** und **_fseeki64** verschiebt der Dateizeiger (sofern vorhanden) zugeordneten Funktionen *Stream* an einem neuen Speicherort, der *Offset* Bytes vom *Ursprung*. Der nächste Vorgang im Stream tritt am neuen Speicherort auf. Für einen updatebereiten Stream kann der nächste Vorgang ein Lese- oder Schreibvorgang sein. Das Argument *Ursprung* muss eines der folgenden Konstanten in STDIO definiert sein. H

|Ursprungswert|Bedeutung|
|-|-|
**SEEK_CUR**|Aktuelle Position des Dateizeigers
**SEEK_END**|Ende der Datei
**SEEK_SET**|Anfang der Datei

Sie können **Fseek** und **_fseeki64** um den Zeiger an einer beliebigen Stelle in einer Datei neu zu positionieren. Der Zeiger kann auch nach dem Ende der Datei positioniert werden. **Fseek** und **_fseeki64** löscht den Dateiende-Indikator und neutralisiert die Wirkung der vorherige [Ungetc](ungetc-ungetwc.md) gegen ruft *Stream*.

Wenn eine Datei zum Anfügen von Daten geöffnet wird, wird die aktuelle Dateiposition vom letzten E/A-Vorgang nicht dadurch bestimmt, wo der nächste Schreibvorgang erfolgt. Wenn noch kein E/A-Vorgang für eine zum Anhängen geöffnete Datei stattgefunden hat, ist die Dateiposition der Anfang der Datei.

Für Streams, die im Textmodus geöffnet **Fseek** und **_fseeki64** verwenden, haben beschränkt werden, da Carriage Return-Zeilenvorschub Übersetzungen können dazu führen, dass **Fseek** und **_ fseeki64** zu unerwarteten Ergebnissen führen. Die einzige **Fseek** und **_fseeki64** Vorgänge im Textmodus geöffnet Datenstreams funktioniert auf alle Fälle sind:

- Suchen mit einem Offset von 0 hinsichtlich der ursprünglichen Werte

- Suchvorgänge vom Anfang der Datei mit einem Offset-Wert zurückgegeben, Aufrufen von [Ftell](ftell-ftelli64.md) Verwendung **Fseek** oder [_ftelli64](ftell-ftelli64.md) Verwendung **_fseeki64**.

Im Textmodus wird STRG+Z als ein Dateiendezeichen in der Eingabe interpretiert. In den Dateien geöffnet zum Lesen/Schreiben [Fopen](fopen-wfopen.md) und alle zugehörige Routinen überprüfen Sie STRG + z am Ende der Datei, und entfernen Sie sie nach Möglichkeit. Dies geschieht, weil die Kombination mit **Fseek** und [Ftell](ftell-ftelli64.md) oder **_fseeki64** und [_ftelli64](ftell-ftelli64.md), zum Navigieren innerhalb einer Datei, die mit endet STRG + Z verursachen **Fseek** oder **_fseeki64** gegen Ende der Datei nicht ordnungsgemäß verhält.

Wenn CRT eine Datei öffnet, die mit einer Bytereihenfolge-Marke (Byte Order Mark, BOM) beginnt, wird der Dateizeiger nach der BOM positioniert (d.h. am Anfang des tatsächlichen Dateiinhalts). Sie ggf. **Fseek** verwenden, um den Anfang der Datei [Ftell](ftell-ftelli64.md) abzurufenden Anfangsposition und **Fseek** , statt an position 0.

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
