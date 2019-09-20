---
title: _getdrive
ms.date: 09/19/2019
api_name:
- _getdrive
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
- _getdrive
- getdrive
helpviewer_keywords:
- current disk drive
- getdrive function
- disk drives
- _getdrive function
ms.assetid: e40631a0-8f1a-4897-90ac-e1037ff30bca
ms.openlocfilehash: 94d6c15270827cf61ec6086de8fa11251b435e2c
ms.sourcegitcommit: f907b15f50a6b945d0b87c03af0050946157d701
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "71158767"
---
# <a name="_getdrive"></a>_getdrive

Ruft das aktuelle Laufwerk ab.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _getdrive( void );
```

## <a name="return-value"></a>Rückgabewert

Gibt das aktuelle (Standard-)Laufwerk zurück (1 = A, 2 = B usw.). Der Rückgabewert 0 (null) bedeutet, dass der aktuelle Pfad nicht mit dem Namen eines Buch Laufwerks, z. b. einem UNC-Pfad, beginnt. Oder es bedeutet, dass eine interne Puffer Zuordnung fehlgeschlagen ist. Wenn eine interne Zuordnung fehlschlägt `errno` , wird auf ENOMEM festgelegt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_getdrive**|\<direct.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_getdrive.c
// compile with: /c
// Illustrates drive functions including:
//    _getdrive       _chdrive        _getdcwd
//

#include <stdio.h>
#include <direct.h>
#include <stdlib.h>
#include <ctype.h>

int main( void )
{
   int ch, drive, curdrive;
   static char path[_MAX_PATH];

   // Save current drive.
   curdrive = _getdrive();

   printf( "Available drives are:\n" );

   // If we can switch to the drive, it exists.
   for( drive = 1; drive <= 26; drive++ )
   {
      if( !_chdrive( drive ) )
      {
         printf( "%c:", drive + 'A' - 1 );
         if( _getdcwd( drive, path, _MAX_PATH ) != NULL )
            printf( " (Current directory is %s)", path );
         putchar( '\n' );
      }
   }

   // Restore original drive.
   _chdrive( curdrive );
}
```

```Output
Available drives are:
A: (Current directory is A:\)
C: (Current directory is C:\)
E: (Current directory is E:\testdir\bin)
F: (Current directory is F:\)
G: (Current directory is G:\)
```

## <a name="see-also"></a>Siehe auch

[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[_chdrive](chdrive.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
