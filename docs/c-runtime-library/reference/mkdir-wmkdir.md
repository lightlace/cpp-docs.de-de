---
title: _mkdir, _wmkdir
ms.date: 11/04/2016
api_name:
- _wmkdir
- _mkdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mkdir
- tmkdir
- _tmkdir
- wmkdir
- _wmkdir
helpviewer_keywords:
- _wmkdir function
- folders [C++], creating
- wmkdir function
- directories [C++], creating
- mkdir function
- tmkdir function
- _mkdir function
- _tmkdir function
ms.assetid: 7f22d01d-63a5-4712-a6e7-d34878b2d840
ms.openlocfilehash: 0d2fd45b566909a61a04a5cabb34c74b9b253430
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951719"
---
# <a name="_mkdir-_wmkdir"></a>_mkdir, _wmkdir

Erstellt ein neues Verzeichnis.

## <a name="syntax"></a>Syntax

```C

int _mkdir(
   const char *dirname
);
int _wmkdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>Parameter

*dirname*<br/>
Der Pfad für ein neues Verzeichnis.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt den Wert 0 zurück, wenn das neue Verzeichnis erstellt wurde. Bei einem Fehler gibt die Funktion-1 zurück und legt **errno** wie folgt fest.

**EEXIST** Das Verzeichnis wurde nicht erstellt, da *dirname* der Name einer vorhandenen Datei, eines Verzeichnisses oder eines Geräts ist.

**ENOENT** Der Pfad wurde nicht gefunden.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_mkdir** -Funktion erstellt ein neues Verzeichnis mit dem angegebenen *dirname.* **_mkdir** kann pro Rückruf nur ein neues Verzeichnis erstellen, sodass nur die letzte Komponente von *dirname* ein neues Verzeichnis benennen kann. **_mkdir** übersetzt keine Pfad Trennzeichen. Unter Windows NT sind sowohl der umgekehrte Schrägstrich (\\) als auch der Schrägstrich () gültige Pfadtrennzeichen in Zeichenfolgen in Laufzeitroutinen.

**_wmkdir** ist eine breit Zeichen Version von **_mkdir**. Das *dirname* -Argument für **_wmkdir** ist eine Zeichenfolge mit breit Zeichen. **_wmkdir** und **_mkdir** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmkdir**|**_mkdir**|**_mkdir**|**_wmkdir**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mkdir**|\<direct.h>|
|**_wmkdir**|\<direct.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_makedir.c

#include <direct.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   if( _mkdir( "\\testtmp" ) == 0 )
   {
      printf( "Directory '\\testtmp' was successfully created\n" );
      system( "dir \\testtmp" );
      if( _rmdir( "\\testtmp" ) == 0 )
        printf( "Directory '\\testtmp' was successfully removed\n"  );
      else
         printf( "Problem removing directory '\\testtmp'\n" );
   }
   else
      printf( "Problem creating directory '\\testtmp'\n" );
}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Directory '\testtmp' was successfully created
Volume in drive C has no label.
Volume Serial Number is E078-087A

Directory of C:\testtmp

02/12/2002  09:56a      <DIR>          .
02/12/2002  09:56a      <DIR>          ..
               0 File(s)              0 bytes
               2 Dir(s)  15,498,690,560 bytes free
Directory '\testtmp' was successfully removed
```

## <a name="see-also"></a>Siehe auch

[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
