---
title: _get_timezone
ms.date: 11/04/2016
apiname:
- _get_timezone
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_timezone
- get_timezone
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
ms.openlocfilehash: 26cf8114ab766bdb394d2db9ad5842622a447bd1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613914"
---
# <a name="gettimezone"></a>_get_timezone

Ruft den Unterschied in Sekunden zwischen Coordinated Universal Time (UTC) und Ortszeit ab.

## <a name="syntax"></a>Syntax

```C
error_t _get_timezone(
    long* seconds
);
```

### <a name="parameters"></a>Parameter

*Sekunden*<br/>
Der Unterschied in Sekunden zwischen UTC und Ortszeit.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg NULL oder eine **Errno** -Wert, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Die **_get_timezone** Funktion ruft den Unterschied in Sekunden zwischen UTC und Ortszeit als Ganzzahl ab. Der Standardwert beträgt 28.800 Sekunden für Pacific Standard Time (acht Stunden nach UTC).

Wenn *Sekunden* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **EINVAL**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_timezone**|\<time.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_tzname](get-tzname.md)<br/>
