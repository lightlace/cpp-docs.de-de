---
title: tmpfile
ms.date: 11/04/2016
apiname:
- tmpfile
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
- tmpfile
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
ms.openlocfilehash: 98afcb7a3e04a96a1b08bc1b975634153e550839
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530324"
---
# <a name="tmpfile"></a>tmpfile

Erstellt eine temporäre Datei. Diese Funktion ist veraltet, da eine sicherere Version verfügbar ist. Sie finden sie unter [tmpfile_s](tmpfile-s.md).

## <a name="syntax"></a>Syntax

```C
FILE *tmpfile( void );
```

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **Tmpfile** einen streamzeiger zurück. Andernfalls wird eine **NULL** Zeiger.

## <a name="remarks"></a>Hinweise

Die **Tmpfile** Funktion erstellt eine temporäre Datei und gibt einen Zeiger auf den Stream. Die temporäre Datei wird im Stammverzeichnis erstellt. Verwenden Sie zum Erstellen einer temporären Datei in einem anderen Verzeichnis als dem Stammverzeichnis [tmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) oder [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) in Verbindung mit [fopen](fopen-wfopen.md).

Wenn die Datei kann nicht geöffnet werden, **Tmpfile** gibt eine **NULL** Zeiger. Diese temporäre Datei wird automatisch gelöscht, wenn die Datei geschlossen wird, wenn das Programm beendet, normalerweise, oder wenn wird, **_rmtmp** aufgerufen wird, unter der Annahme, dass das aktuelle Arbeitsverzeichnis nicht ändert. Die temporäre Datei wird geöffnet, **w + b** (binären Lese-/Schreib-) Modus.

Fehler kann auftreten, wenn Sie, mehr als TMP_MAX versuchen (Siehe STDIO. H) Aufrufe mit **Tmpfile**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**tmpfile**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

> [!NOTE]
> Für dieses Beispiel benötigen Sie Administratorrechte, um es unter Windows Vista auszuführen.

```C
// crt_tmpfile.c
// compile with: /W3
// This program uses tmpfile to create a
// temporary file, then deletes this file with _rmtmp.
#include <stdio.h>

int main( void )
{
   FILE *stream;
   int  i;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      if( (stream = tmpfile()) == NULL ) // C4996
      // Note: tmpfile is deprecated; consider using tmpfile_s instead
         perror( "Could not open new temporary file\n" );
      else
         printf( "Temporary file %d was created\n", i );
   }

   // Remove temporary files.
   printf( "%d temporary files deleted\n", _rmtmp() );
}
```

```Output
Temporary file 1 was created
Temporary file 2 was created
Temporary file 3 was created
3 temporary files deleted
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_rmtmp](rmtmp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
