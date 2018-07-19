---
title: _mkdir, _wmkdir | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wmkdir
- _mkdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mkdir
- tmkdir
- _tmkdir
- wmkdir
- _wmkdir
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40641911af9c61285049a5943cdc8f5c21cba99b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402139"
---
# <a name="mkdir-wmkdir"></a>_mkdir, _wmkdir

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

*Verwendung*<br/>
Der Pfad für ein neues Verzeichnis.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt den Wert 0 zurück, wenn das neue Verzeichnis erstellt wurde. Auf einen Fehler, die Funktion gibt-1 zurück und stellt **Errno** wie folgt.

**EEXIST** Verzeichnis wurde nicht erstellt werden, da *Dirname* ist der Name einer vorhandenen Datei, Verzeichnis oder Gerät.

**ENOENT** Pfad wurde nicht gefunden.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_mkdir** Funktion erstellt ein neues Verzeichnis mit dem angegebenen *Dirname.* **_mkdir** können nur ein neues Verzeichnis pro Aufruf, sodass nur die letzte Komponente erstellen *Dirname* können Sie ein neues Verzeichnis benennen. **_mkdir** Pfadtrennzeichen nicht übersetzt. Unter Windows NT sind sowohl der umgekehrte Schrägstrich (\\) als auch der Schrägstrich () gültige Pfadtrennzeichen in Zeichenfolgen in Laufzeitroutinen.

**_wmkdir** ist eine Breitzeichen-Version von **_mkdir**; das *Dirname* Argument **_wmkdir** ist eine Breitzeichen-Zeichenfolge. **_wmkdir** und **_mkdir** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmkdir**|**_mkdir**|**_mkdir**|**_wmkdir**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
