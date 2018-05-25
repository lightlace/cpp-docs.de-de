---
title: _get_tzname | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_tzname
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
- _get_tzname
- get_tzname
dev_langs:
- C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4b49aa404dda6234382ae461459dece64e5996d
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
---
# <a name="gettzname"></a>_get_tzname

Ruft die Darstellung der Zeichenfolge vom Namen der Zeitzone oder den Name der Standard-Sommerzeitzone (DST) ab.

## <a name="syntax"></a>Syntax

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>Parameter

*pReturnValue*<br/>
Länge der Zeichenfolge *TimeZoneName* einschließlich null-Abschlusszeichen.

*timeZoneName*<br/>
Die Adresse einer Zeichenfolge für die Darstellung der Zeitzonenname oder der Sommerzeit Normalzeit Zonenname (DST), je nach *Index*.

*sizeInBytes*<br/>
Die Größe der *TimeZoneName* Zeichenfolge in Bytes.

*index*<br/>
Der Index eines der zwei abzurufenden Zeitzonen.

## <a name="return-value"></a>Rückgabewert

NULL Wenn erfolgreich, andernfalls ein **Errno** Typwert.

Wenn entweder *TimeZoneName* ist **NULL**, oder *SizeInBytes* 0 (null) oder kleiner als 0 (null) (aber nicht beides), ein Handler für ungültige Parameter aufgerufen wird, wie in beschrieben [ Überprüfen der Parameter](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt **EINVAL**.

### <a name="error-conditions"></a>Fehlerbedingungen

|*pReturnValue*|*timeZoneName*|*sizeInBytes*|*index*|Rückgabewert|Inhalt der *TimeZoneName*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|Größe des ZZ-Namens|**NULL**|0|0 oder 1|0|nicht geändert|
|Größe des ZZ-Namens|alle|> 0|0 oder 1|0|ZZ-Name|
|nicht geändert|**NULL**|> 0|alle|**EINVAL**|nicht geändert|
|nicht geändert|alle|Null|alle|**EINVAL**|nicht geändert|
|nicht geändert|alle|> 0|> 1|**EINVAL**|nicht geändert|

## <a name="remarks"></a>Hinweise

Die **_get_tzname** Funktion ruft die Zeichenfolge zeichendarstellung der Zeitzone oder der Sommerzeit Normalzeit Zonenname (DST) in die Adresse des *TimeZoneName* je nach den Index Wert, zusammen mit der Größe der Zeichenfolge in *pReturnValue*. Wenn *TimeZoneName* ist **NULL** und *SizeInBytes* gleich NULL ist, werden nur die Größe der Zeichenfolge entweder Time Zone in Bytes wird zurückgegeben, in *pReturnValue*. Die Indexwerte müssen entweder für Standard-Zeitzonen 0 oder 1 für Standard-Sommerzeitzonen betragen. Alle anderen Indexwerte haben unbestimmte Ergebnisse.

### <a name="index-values"></a>Indexwerte

|*index*|Inhalt der *TimeZoneName*|*TimeZoneName* Standardwert|
|-------------|--------------------------------|----------------------------------|
|0|Name der Zeitzone|„PST“|
|1|Name der Standard-Sommerzeitzone|„PDT“|
|> 1 oder < 0|**Errno** festgelegt **EINVAL**|nicht geändert|

Werden die Werte nicht ausdrücklich während der Laufzeit geändert, sind die Standardwerte „PST“ und „PDT“.  Die Größe dieser Zeichenarrays unterliegen **TZNAME_MAX** Wert.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[TZNAME_MAX](../../c-runtime-library/tzname-max.md)<br/>
