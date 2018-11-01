---
title: _set_doserrno
ms.date: 11/04/2016
apiname:
- _set_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_doserrno
- set_doserrno
helpviewer_keywords:
- _set_doserrno function
- doserrno global variable
- set_doserrno function
- _doserrno global variable
ms.assetid: 8686c159-3797-4705-a53e-7457869ca6f3
ms.openlocfilehash: a99d63b03aebd4a54ac50e98d5e5752e741fec85
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607297"
---
# <a name="setdoserrno"></a>_set_doserrno

Legt den Wert der globalen Variable [_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) fest.

## <a name="syntax"></a>Syntax

```C
errno_t _set_doserrno( int error_value );
```

### <a name="parameters"></a>Parameter

*error_value*<br/>
Der neue Wert des **_doserrno**.

## <a name="return-value"></a>Rückgabewert

Gibt 0 zurück, wenn erfolgreich.

## <a name="remarks"></a>Hinweise

Mögliche Werte sind in Errno.h definiert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_set_doserrno**|\<stdlib.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_get_doserrno](get-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
