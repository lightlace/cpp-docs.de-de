---
title: _chdrive | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b6d8d53ea3b7331de08ea2aa2a00e5fdfb106c8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684322"
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

*Laufwerk*<br/>
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
