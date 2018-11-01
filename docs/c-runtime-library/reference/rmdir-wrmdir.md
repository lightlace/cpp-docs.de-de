---
title: _rmdir, _wrmdir
ms.date: 11/04/2016
apiname:
- _wrmdir
- _rmdir
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
- trmdir
- _trmdir
- wrmdir
- _rmdir
- _wrmdir
helpviewer_keywords:
- _rmdir function
- directories [C++], deleting
- rmdir function
- directories [C++], removing
- trmdir function
- _trmdir function
- _wrmdir function
- wrmdir function
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
ms.openlocfilehash: 1169405ae2f03a1e6affe2fcc00d594912e08ae1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511123"
---
# <a name="rmdir-wrmdir"></a>_rmdir, _wrmdir

Löscht ein Verzeichnis.

## <a name="syntax"></a>Syntax

```C
int _rmdir(
   const char *dirname
);
int _wrmdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>Parameter

*DirName*<br/>
Der Pfad des Verzeichnisses, das entfernt werden soll.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt 0 zurück, wenn das Verzeichnis erfolgreich gelöscht wird. Der Rückgabewert 1 gibt an, einen Fehler und **Errno** auf einen der folgenden Werte festgelegt:

|errno-Wert|Bedingung|
|-|-|
**ENOTEMPTY**|Die angegebene Pfad ist kein Verzeichnis, das Verzeichnis ist nicht leer oder das Verzeichnis ist das aktuelle Arbeitsverzeichnis oder das Stammverzeichnis.
**ENOENT**|Der Pfad ist ungültig.
**EACCES**|Ein Programm verfügt über ein geöffnetes Handle des Verzeichnisses.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_rmdir** Funktion löscht die im angegebenen Verzeichnis *Dirname*. Das Verzeichnis muss leer sein, und es darf sich nicht um das aktuelle Arbeitsverzeichnis oder das Stammverzeichnis handeln.

**_wrmdir** ist eine Breitzeichen-Version von **_rmdir**; die *Dirname* Argument **_wrmdir** ist eine Breitzeichen-Zeichenfolge. **_wrmdir** und **_rmdir** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_trmdir**|**_rmdir**|**_rmdir**|**_wrmdir**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_rmdir**|\<direct.h>|
|**_wrmdir**|\<direct.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Siehe Beispiele für [_mkdir](mkdir-wmkdir.md).

## <a name="see-also"></a>Siehe auch

[Verzeichnissteuerung](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
