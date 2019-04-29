---
title: _chdrive
ms.date: 11/04/2016
apiname:
- _chdrive
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
- chdrive
- _chdrive
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
ms.openlocfilehash: 963b7b7b40b632981abfc1529beb9c48a5b991ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335476"
---
# <a name="chdrive"></a>_chdrive

Ändert das aktuelle Laufwerk.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>Parameter

*drive*<br/>
Eine ganze Zahl von 1 bis 26, die das aktuelle Laufwerk angibt (1=A, 2=B usw.).

## <a name="return-value"></a>Rückgabewert

Null (0), wenn das aktuelle Laufwerk erfolgreich geändert wurde; andernfalls – 1.

## <a name="remarks"></a>Hinweise

Wenn *Laufwerk* ist nicht im Bereich von 1 bis 26, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die **_chdrive** Funktion – 1 zurück, **Errno** nastaven NA hodnotu **EACCES**, und **_doserrno** nastaven NA hodnotu  **ERROR_INVALID_DRIVE**.

Die Funktion **_chdrive** ist nicht threadsicher, da sie von der Funktion **SetCurrentDirectory** abhängt, die selbst nicht threadsicher ist. Um **_chdrive** sicher in einer Multithreadanwendung zu verwenden, müssen Sie eine eigene Threadsynchronisierung bereitstellen. Weitere Informationen finden Sie unter [SetCurrentDirectory](/windows/desktop/api/winbase/nf-winbase-setcurrentdirectory).

Die Funktion **_chdrive** ändert nur das aktuelle Arbeitslaufwerk; **_chdir** ändert das aktuelle Arbeitsverzeichnis.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_chdrive**|\<direct.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Beachten Sie das Beispiel für [_getdrive](getdrive.md).

## <a name="see-also"></a>Siehe auch

[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
