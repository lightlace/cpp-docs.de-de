---
title: _access, _waccess | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _access
- _waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
dev_langs:
- C++
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ada1377efea8bd05dea1fd59dbbe6cd4495e6ea2
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404641"
---
# <a name="access-waccess"></a>_access, _waccess

Legt fest, ob eine Datei schreibgeschützt ist. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_access_s, waccess_s](access-s-waccess-s.md).

## <a name="syntax"></a>Syntax

```C
int _access(
   const char *path,
   int mode
);
int _waccess(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>Parameter

*path*  
Datei oder Verzeichnispfad.

*mode*  
Lese-/Schreibattribut.

## <a name="return-value"></a>Rückgabewert

Jede Funktion gibt 0 zurück, wenn sich die Datei im angegebenen Modus befindet. Die Funktion gibt-1 zurück, wenn die angegebene Datei nicht vorhanden ist oder verfügt nicht über den angegebenen Modus; In diesem Fall `errno` festgelegt ist, wie in der folgenden Tabelle gezeigt.

|||
|-|-|
`EACCES`|Zugriff verweigert: Aufgrund der Berechtigungen wird der Zugriff im angegebenen Modus verweigert.
`ENOENT`|Der Dateiname oder der Pfad wurde nicht gefunden.
`EINVAL`|Ungültiger Parameter.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Bei Verwendung mit Dateien, die **_access** Funktion bestimmt, ob die angegebene Datei oder das Verzeichnis vorhanden ist und deren Attribute durch den Wert des *Modus*. Bei Verwendung mit Verzeichnissen **_access** bestimmt nur, ob das angegebene Verzeichnis vorhanden ist; in Windows 2000 und späteren Betriebssystemen alle Verzeichnisse Lese- und Schreibzugriff.

|*Modus* Wert|überprüft nur, ob die Datei|
|------------------|---------------------|
|00|existiert|
|02|Nur Schreibzugriff|
|04|Schreibgeschützt|
|06|Lesen und Schreiben|

Diese Funktion überprüft nur, ob die Datei oder das Verzeichnis schreibgeschützt sind. Es überprüft jedoch nicht die Dateisystem-Sicherheitseinstellungen. Dafür benötigen Sie ein Zugriffstoken. Weitere Informationen zur Dateisystemsicherheit finden Sie unter [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909). Für diese Funktion gibt es eine ATL-Klasse. Weitere Informationen finden Sie unter [CAccessToken-Klasse](../../atl/reference/caccesstoken-class.md).

**_waccess** ist eine Breitzeichen-Version von **_access**; die *Pfad* Argument **_waccess** ist eine Breitzeichen-Zeichenfolge. **_waccess** und **_access** Verhalten sich andernfalls identisch.

Diese Funktion überprüft ihre Parameter. Wenn *Pfad* ist NULL oder *Modus* gibt keinen gültigen Modus, den Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, legt die Funktion `errno` auf `EINVAL` fest und gibt -1 zurück.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess`|**_access**|**_access**|**_waccess**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionale Header|
|-------------|---------------------|----------------------|
|**_access**|\<io.h>|\<errno.h>|
|**_waccess**|\<wchar.h> oder \<io.h>|\<errno.h>|

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird **_access** , überprüfen Sie die Datei mit dem Namen Crt_ACCESS. C, um festzustellen, ob es vorhanden ist und ob Schreiben zulässig ist.

```C
// crt_access.c
// compile with: /W1
// This example uses _access to check the file named
// crt_ACCESS.C to see if it exists and if writing is allowed.

#include  <io.h>
#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    // Check for existence.
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )
    {
        printf_s( "File crt_ACCESS.C exists.\n" );

        // Check for write permission.
        // Assume file is read-only.
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );
    }
}
```

```Output
File crt_ACCESS.C exists.
File crt_ACCESS.C does not have write permission.
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)  
[_chmod, _wchmod](chmod-wchmod.md)  
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)  
[_open, _wopen](open-wopen.md)  
[_stat- und _wstat-Funktionen](stat-functions.md)  