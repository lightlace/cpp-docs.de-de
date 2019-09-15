---
title: _rmdir, _wrmdir
ms.date: 11/04/2016
api_name:
- _wrmdir
- _rmdir
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
ms.openlocfilehash: 396e620bfabe240638dc070ff87582b16287ff60
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949218"
---
# <a name="_rmdir-_wrmdir"></a>_rmdir, _wrmdir

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

*dirname*<br/>
Der Pfad des Verzeichnisses, das entfernt werden soll.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt 0 zurück, wenn das Verzeichnis erfolgreich gelöscht wird. Der Rückgabewert-1 gibt einen Fehler an, und **errno** wird auf einen der folgenden Werte festgelegt:

|errno-Wert|Bedingung|
|-|-|
| **ENOTEMPTY** | Die angegebene Pfad ist kein Verzeichnis, das Verzeichnis ist nicht leer oder das Verzeichnis ist das aktuelle Arbeitsverzeichnis oder das Stammverzeichnis. |
| **ENOENT** | Der Pfad ist ungültig. |
| **EACCES** | Ein Programm verfügt über ein geöffnetes Handle des Verzeichnisses. |

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_rmdir** -Funktion löscht das von *dirname*angegebene Verzeichnis. Das Verzeichnis muss leer sein, und es darf sich nicht um das aktuelle Arbeitsverzeichnis oder das Stammverzeichnis handeln.

**_wrmdir** ist eine breit Zeichen Version von **_rmdir**. Das *dirname* -Argument für **_wrmdir** ist eine Zeichenfolge mit breit Zeichen. **_wrmdir** und **_rmdir** Verhalten sich andernfalls identisch.

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
