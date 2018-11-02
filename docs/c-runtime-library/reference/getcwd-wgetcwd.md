---
title: _getcwd, _wgetcwd
ms.date: 11/04/2016
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
ms.openlocfilehash: 4c533f0e716cb9a13c152b9be3c46f60291118d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520237"
---
# <a name="getcwd-wgetcwd"></a>_getcwd, _wgetcwd

Ruft das aktuelle Arbeitsverzeichnis ab.

## <a name="syntax"></a>Syntax

```C
char *_getcwd(
   char *buffer,
   int maxlen
);
wchar_t *_wgetcwd(
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für den Pfad.

*maxlen*<br/>
Maximale Länge des Pfads in Zeichen: **Char** für **_getcwd** und **"wchar_t"** für **_wgetcwd**.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf *Puffer*. Ein **NULL** Rückgabewert gibt einen Fehler an und **Errno** entweder auf festgelegt ist **ENOMEM**, gibt an, dass nicht genügend Arbeitsspeicher zuordnen *Maxlen* Bytes (Wenn eine **NULL** Argument erhält als *Puffer*), oder **ERANGE**, der angibt, dass der Pfad länger als *Maxlen*  Zeichen. Wenn *Maxlen* ist kleiner als oder gleich 0 (null), ruft diese Funktion einen Handler für ungültige Parameter wie beschrieben in [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_getcwd** Funktion ruft den vollständigen Pfad des aktuellen Arbeitsverzeichnisses für das Standardlaufwerk ab und speichert ihn unter *Puffer*. Das ganzzahlige Argument *Maxlen* gibt die maximale Länge für den Pfad. Ein Fehler auftritt, wenn die Länge des Pfads (einschließlich des abschließenden Zeichens Null) überschreitet *Maxlen*. Die *Puffer* -Argument kann es sich **NULL**; einen Puffer mit mindestens der Größe *Maxlen* (mehr nur bei Bedarf) wird automatisch zugeordnet und mit **Malloc**, um den Pfad zu speichern. Dieser Puffer kann später geleert werden, durch den Aufruf **kostenlose** und an Sie übergeben die **_getcwd** Rückgabewert (einen Zeiger auf den zugeordneten Puffer).

**_getcwd** gibt eine Zeichenfolge, die den Pfad des aktuellen Arbeitsverzeichnisses repräsentiert. Wenn das aktuelle Arbeitsverzeichnis das Stammverzeichnis ist, endet die Zeichenfolge mit einem umgekehrten Schrägstrich ( **\\** ). Wenn das aktuelle Arbeitsverzeichnis nicht das Stammverzeichnis ist, endet die Zeichenfolge mit dem Verzeichnisnamen und nicht mit einem umgekehrten Schrägstrich.

**_wgetcwd** ist eine Breitzeichen-Version von **_getcwd**; die *Puffer* Argument- und Rückgabetypen Wert **_wgetcwd** sind Breitzeichen Zeichenfolgen. **_wgetcwd** und **_getcwd** Verhalten sich andernfalls identisch.

Wenn **_DEBUG** und **_CRTDBG_MAP_ALLOC** definiert sind, werden Aufrufe von **_getcwd** und **_wgetcwd** werden durch Aufrufe von ersetzt **_ Getcwd_dbg** und **_wgetcwd_dbg** zum Debuggen von speicherbelegungen zuzulassen. Weitere Informationen finden Sie unter [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_getcwd**|\<direct.h>|
|**_wgetcwd**|\<direct.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>Siehe auch

[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
