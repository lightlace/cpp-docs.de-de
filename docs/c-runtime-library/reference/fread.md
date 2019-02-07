---
title: fread
ms.date: 11/28/2018
apiname:
- fread
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
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: 7248eb08409b50d855dbb70c7638a856302b345b
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849970"
---
# <a name="fread"></a>fread

Liest Daten aus einem Stream

## <a name="syntax"></a>Syntax

```C
size_t fread(
   void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für Daten.

*size*<br/>
Elementgröße in Bytes

*count*<br/>
Maximale Anzahl der zu lesenden Elemente.

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**Fread** gibt die Anzahl der Elemente vollständig tatsächlich gelesen werden, die möglicherweise weniger als *Anzahl* , wenn ein Fehler auftritt oder das Ende der Datei, vor dem erreichen gefunden wird *Anzahl*. Verwenden der **Feof** oder **Ferror** Funktion, um einen Lesefehler von einer End-of-File-Bedingung zu unterscheiden. Wenn *Größe* oder *Anzahl* ist 0 (null) **Fread** gibt 0 und die pufferinhalte bleiben unverändert. Wenn *Stream* oder *Puffer* ist ein null-Zeiger **Fread** wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt 0 zurück.

Finden Sie unter [ \_Doserrno, Errno, \_Sys\_Errlist, und \_Sys\_Nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) für Weitere Informationen zu diesen Fehlercodes.

## <a name="remarks"></a>Hinweise

Die **Fread** Funktion liest bis zum *Anzahl* Elemente *Größe* Bytes aus dem Eingabe- *Stream* und speichert diese im *Puffer* . Der Dateizeiger *Stream* (sofern vorhanden) wird durch die Anzahl tatsächlich gelesener Bytes erhöht. Wenn in der angegebene Stream geöffnet ist [Textmodus](../../c-runtime-library/text-and-binary-mode-file-i-o.md), Windows-Stil Zeilenumbrüche in Zeilenumbrüche für Unix-Format konvertiert werden. D. h. werden Carriage Return-Zeilenvorschub (CR) Paare durch Zeilenvorschubzeichen (LF) ersetzt. Dieser Vorgang hat keine Auswirkung auf den Dateizeiger oder den Rückgabewert. Die Position des Dateizeigers ist unbestimmt, wenn ein Fehler auftritt. Der Wert eines teilweise gelesenen Elements kann nicht bestimmt werden.

Wenn auf einem Textstream-Modus verwendet werden soll, wenn die Menge der Daten angefordert (d. h. *Größe* \* *Anzahl*) ist größer als oder gleich der internen **Datei** \*Puffergröße (standardmäßig, die dies ist 4096 Bytes, mit konfigurierbaren [Setvbuf](../../c-runtime-library/reference/setvbuf.md)), Streamen von Daten direkt in den vom Benutzer bereitgestellte Puffer kopiert und neue-Zeile-Konvertierung erfolgt in diesem Puffer. Da die konvertierten Daten kürzer als das Streamen von Daten in den Puffer, die Daten der letzten kopiert möglicherweise *Puffer*\[*Return_value* \* *Größe*] () wo *Return_value* ist der Rückgabewert von **Fread**) kann die nicht konvertierte Daten aus der Datei enthalten. Aus diesem Grund empfehlen wir für Sie Null-beenden Zeichendaten auf *Puffer*\[*Return_value* \* *Größe*] ist die Absicht des Puffers als eine Zeichenfolge im C-Stil zu fungieren. Finden Sie unter [Fopen](fopen-wfopen.md) Weitere Informationen zu den Auswirkungen der Textmodus und Binärmodus.

Diese Funktion sperrt alle anderen Threads. Wenn Sie eine nicht sperrende Version benötigen, verwenden Sie **_fread_nolock**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fread**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fread.c
// This program opens a file named FREAD.OUT and
// writes 25 characters to the file. It then tries to open
// FREAD.OUT and read in 25 characters. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   // Open file in text mode:
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )
   {
      for ( i = 0; i < 25; i++ )
         list[i] = (char)('z' - i);
      // Write 25 characters to stream
      numwritten = fwrite( list, sizeof( char ), 25, stream );
      printf( "Wrote %d items\n", numwritten );
      fclose( stream );

   }
   else
      printf( "Problem opening the file\n" );

   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )
   {
      // Attempt to read in 25 characters
      numread = fread( list, sizeof( char ), 25, stream );
      printf( "Number of items read = %d\n", numread );
      printf( "Contents of buffer = %.25s\n", list );
      fclose( stream );
   }
   else
      printf( "File could not be opened\n" );
}
```

```Output
Wrote 25 items
Number of items read = 25
Contents of buffer = zyxwvutsrqponmlkjihgfedcb
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[Text- und binäre Datei-e/a](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
