---
title: fgetpos | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b111a911083354c8d9478b2c914a0a5f7dfe7725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397384"
---
# <a name="fgetpos"></a>fgetpos

Ruft den Dateipositionsindikator eines Streams ab

## <a name="syntax"></a>Syntax

```C
int fgetpos(
   FILE *stream,
   fpos_t *pos
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Der Zielstream

*POS*<br/>
Speicher des Positionsindikators

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **Fgetpos** gibt 0 zurück. Bei einem Fehler, es gibt einen Wert ungleich NULL zurück und legt **Errno** auf einen der folgenden Manifestkonstanten (definiert in STDIO. H): **EBADF**, ist kein gültiger Dateizeiger oder kann nicht zugegriffen werden, was bedeutet, dass im angegebenen Stream oder **EINVAL**, dies bedeutet, dass die *Stream* Wert oder den Wert des *pos* ist ungültig, z. B. If ist ein null-Zeiger. Wenn *Stream* oder *pos* ist ein **NULL** -Zeiger ist, ruft die Funktion den Handler für ungültige Parameter an, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Hinweise

Die **Fgetpos** Funktion ruft den aktuellen Wert der *Stream* des Arguments dateipositionszeiger und speichert ihn in das Objekt verweist *pos*. Die **Fsetpos** -Funktion kann in gespeicherten Informationen später verwenden *pos* zum Zurücksetzen der *Stream* argumentzeiger auf seine Position zum Zeitpunkt **Fgetpos** aufgerufen wurde. Die *pos* Wert wird in ein internes Format gespeichert und dient zur Verwendung nur durch **Fgetpos** und **Fsetpos**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fgetpos.c
// This program uses fgetpos and fsetpos to
// return to a location in a file.

#include <stdio.h>

int main( void )
{
   FILE   *stream;
   fpos_t pos;
   char   buffer[20];

   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {
      perror( "Trouble opening file" );
      return -1;
   }

   // Read some data and then save the position.
   fread( buffer, sizeof( char ), 8, stream );
   if( fgetpos( stream, &pos ) != 0 ) {
      perror( "fgetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fgetpos: %.13s\n", buffer );

   // Restore to old position and read data
   if( fsetpos( stream, &pos ) != 0 ) {
      perror( "fsetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fsetpos: %.13s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetpostxt"></a>Eingabe: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crtfgetpostxt"></a>Ausgabe: crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
