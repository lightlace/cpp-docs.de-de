---
title: tmpfile_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- tmpfile_s
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
- tmpfile_s
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cd7866a7135f04aa580910d5ac121311312c542
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412149"
---
# <a name="tmpfiles"></a>tmpfile_s

Erstellt eine temporäre Datei. Dies ist eine Version von [tmpfile](tmpfile.md) mit Sicherheitserweiterungen wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t tmpfile_s(
   FILE** pFilePtr
);
```

### <a name="parameters"></a>Parameter

*pFilePtr*<br/>
Die Adresse eines Zeigers, um die Adresse des generierten Zeigers in einen Stream zu speichern.

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg 0 (null) zurück und einen Fehlercode, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|*pFilePtr*|**Rückgabewert**|**Inhalt der***pFilePtr* |
|----------------|----------------------|---------------------------------|
|**NULL**|**EINVAL**|nicht geändert|

Wenn der obengenannte Parametervalidierungsfehler auftritt, wird der ungültige Parameterhandler wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und der Rückgabewert ist **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **Tmpfile_s** Funktion erstellt eine temporäre Datei und fügt einen Zeiger zu diesem Datenstrom in die *pFilePtr* Argument. Die temporäre Datei wird im Stammverzeichnis erstellt. Verwenden Sie zum Erstellen einer temporären Datei in einem anderen Verzeichnis als dem Stammverzeichnis [tmpnam_s](tmpnam-s-wtmpnam-s.md) oder [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) in Verbindung mit [fopen](fopen-wfopen.md).

Wenn die Datei kann nicht geöffnet werden, **Tmpfile_s** schreibt **NULL** auf die *pFilePtr* Parameter. Diese temporäre Datei wird automatisch gelöscht, wenn die Datei, beim Beenden des Programms normal oder wenn geschlossen ist **_rmtmp** aufgerufen wird, vorausgesetzt, dass das aktuelle Arbeitsverzeichnis nicht ändert. Die temporäre Datei wird geöffnet, **w + b** (Lese-/Schreibzugriff binären) Modus.

Fehler kann auftreten, wenn Sie versuchen, mehr als **TMP_MAX_S** (Siehe STDIO. H) Aufrufe mit **Tmpfile_s**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**tmpfile_s**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

> [!NOTE]
> In diesem Beispiel wird möglicherweise Administratorrechte verfügen, um unter Windows ausgeführt werden.

```C
// crt_tmpfile_s.c
// This program uses tmpfile_s to create a
// temporary file, then deletes this file with _rmtmp.
//

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char tempstring[] = "String to be written";
   int  i;
   errno_t err;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      err = tmpfile_s(&stream);
      if( err )
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
