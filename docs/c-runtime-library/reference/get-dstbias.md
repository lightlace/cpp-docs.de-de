---
title: _get_dstbias
ms.date: 11/04/2016
apiname:
- _get_dstbias
- __dstbias
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
- __dstbias
- _get_dstbias
- get_dstbias
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
ms.openlocfilehash: 61807f854dc9c2f7de6f0acd5bbf4668987ce49e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332376"
---
# <a name="getdstbias"></a>_get_dstbias

Ruft die Sommerzeitverschiebung in Sekunden ab.

## <a name="syntax"></a>Syntax

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>Parameter

*seconds*<br/>
Die Verschiebung der Sommerzeit in Sekunden.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg NULL oder eine **Errno** -Wert, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Die **_get_dstbias** Funktion ruft die Anzahl der Sekunden in der Sommerzeit als Ganzzahl. Wenn die Sommerzeit gültig ist, beträgt die Standardzeitverschiebung 3600 Sekunden. Dies ist die Anzahl der Sekunden in einer Stunde (obwohl in ein paar Regionen eine Zeitverschiebung von zwei Stunden gilt).

Wenn *Sekunden* ist **NULL**, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **EINVAL**.

Es wird empfohlen, diese Funktion statt des Makros **_dstbias** oder der veralteten Funktion **__dstbias**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_dstbias**|\<time.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
