---
title: _get_daylight | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __daylight
- _get_daylight
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
- get_daylight
- _get_daylight
dev_langs:
- C++
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fbe7e36db2e5ca5365f43dc23281d9b5e79077d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398122"
---
# <a name="getdaylight"></a>_get_daylight

Ruft die Sommerzeitverschiebung in Stunden ab.

## <a name="syntax"></a>Syntax

```C
error_t _get_daylight( int* hours );
```

### <a name="parameters"></a>Parameter

*Stunden*<br/>
Die Verschiebung der Sommerzeit in Stunden.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg NULL oder ein **Errno** Wert, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Die **_get_daylight** Funktion ruft die Anzahl der Stunden in der Sommerzeit als Ganzzahl ab. Wenn die Sommerzeit gültig ist, beträgt die Standardzeitverschiebung eine Stunde (obwohl in ein paar Regionen eine Zeitverschiebung von zwei Stunden gilt).

Wenn *Stunden* ist **NULL**, den Handler für ungültige Parameter aufgerufen wird, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt **EINVAL**.

Es wird empfohlen, diese Funktion statt des Makros **_daylight** oder der veralteten Funktion **__daylight**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_get_daylight**|\<time.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
