---
title: _access_s, waccess_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _access_s
- _waccess_s
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
- waccess_s
- access_s
- _waccess_s
- _access_s
dev_langs:
- C++
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24c269951eacfc2f7a5d40c8fad1e4fb67cc1d2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392090"
---
# <a name="accesss-waccesss"></a>_access_s, _waccess_s

Bestimmt die Lese-/Schreibberechtigungen einer Datei. Dies ist eine sicherere Version von [_access, _waccess](access-waccess.md), wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t _access_s(
   const char *path,
   int mode
);
errno_t _waccess_s(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>Parameter

*path*<br/>
Datei oder Verzeichnispfad.

*mode*<br/>
Berechtigungseinstellung.

## <a name="return-value"></a>Rückgabewert

Jede Funktion gibt 0 zurück, wenn sich die Datei im angegebenen Modus befindet. Die Funktion gibt einen Fehlercode zurück, wenn die angegebene Datei nicht vorhanden ist oder im angegebenen Modus nicht auf sie zugegriffen werden kann. In diesem Fall gibt die Funktion einen Fehlercode aus dem Satz wie folgt und setzt auch **Errno** auf den gleichen Wert.

|errno-Wert|Bedingung|
|-|-|
**EACCES**|Zugriff verweigert. Aufgrund der Berechtigungen wird der Zugriff im angegebenen Modus verweigert.
**ENOENT**|Der Dateiname oder der Pfad wurde nicht gefunden.
**EINVAL**|Ungültiger Parameter.

Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Bei Verwendung mit Dateien, die **_access_s** -Funktion bestimmt, ob die angegebene Datei vorhanden ist und kann, als zugegriffen werden durch den Wert der angegebenen *Modus*. Bei Verwendung mit Verzeichnisse **_access_s** bestimmt nur, ob das angegebene Verzeichnis vorhanden ist. Unter Windows 2000 und späteren Betriebssystemen alle Verzeichnisse verfügen über Lese- und Schreibzugriff auf.

|Moduswert|überprüft nur, ob die Datei|
|----------------|---------------------|
|00|existiert.|
|02|Schreibberechtigung.|
|04|Leseberechtigung.|
|06|Lese- und Schreibberechtigung.|

Die Berechtigung zum Lesen oder Schreiben einer Datei garantiert nicht, dass diese Datei auch geöffnet werden kann. Z. B. wenn eine Datei von einem anderen Prozess gesperrt ist, möglicherweise nicht zugegriffen werden kann, obwohl **_access_s** gibt 0 zurück.

**_waccess_s** ist eine Breitzeichen-Version von **_access_s**, wobei die *Pfad* Argument **_waccess_s** ist eine Breitzeichen-Zeichenfolge. Andernfalls **_waccess_s** und **_access_s** Verhalten sich identisch.

Diese Funktionen überprüfen ihre Parameter. Wenn *Pfad* ist **NULL** oder *Modus* gültiger Modus ist, gibt nicht an den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** inventurüberprüfung **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_taccess_s**|**_access_s**|**_access_s**|**_waccess_s**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_access_s**|\<io.h>|\<errno.h>|
|**_waccess_s**|\<wchar.h> oder \<io.h>|\<errno.h>|

## <a name="example"></a>Beispiel

Dieses Beispiel verwendet **_access_s** , überprüfen Sie die Datei mit dem Namen crt_access_s.c, um festzustellen, ob es vorhanden ist und ob Schreibvorgänge zulässig ist.

```C
// crt_access_s.c

#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    errno_t err = 0;

    // Check for existence.
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )
    {
        printf_s( "File crt_access_s.c exists.\n" );

        // Check for write permission.
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )
        {
            printf_s( "File crt_access_s.c does have "
                      "write permission.\n" );
        }
        else
        {
            printf_s( "File crt_access_s.c does not have "
                      "write permission.\n" );
        }
    }
    else
    {
        printf_s( "File crt_access_s.c does not exist.\n" );
    }
}
```

```Output
File crt_access_s.c exists.
File crt_access_s.c does not have write permission.
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat- und _wstat-Funktionen](stat-functions.md)<br/>
