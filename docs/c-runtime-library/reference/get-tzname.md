---
title: _get_tzname
ms.date: 10/22/2018
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
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
ms.openlocfilehash: c173832efb866eed133a908b5f2b72266fd3798a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332039"
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
Länge der Zeichenfolge *TimeZoneName* einschließlich eines null-Terminators.

*timeZoneName*<br/>
Die Adresse einer Zeichenfolge für die Darstellung des Namens der Zeitzone oder der Standard Sommerzeitzone (DST), je nach *Index*.

*sizeInBytes*<br/>
Die Größe der *TimeZoneName* -Zeichenfolge in Bytes.

*index*<br/>
Der Index eines der zwei abzurufenden Zeitzonen.

|*index*|Inhalt der *TimeZoneName*|*TimeZoneName* Standardwert|
|-|-|-|
|0|Name der Zeitzone|„PST“|
|1|Name der Standard-Sommerzeitzone|„PDT“|
|> 1 oder < 0|**Errno** festgelegt **EINVAL**|nicht geändert|

Werden die Werte nicht ausdrücklich während der Laufzeit geändert, sind die Standardwerte „PST“ und „PDT“.

## <a name="return-value"></a>Rückgabewert

NULL, wenn erfolgreich, andernfalls ein **Errno** Typwert.

Wenn entweder *TimeZoneName* ist **NULL**, oder *SizeInBytes* ist 0 (null) oder kleiner als 0 (null) (aber nicht beides), Handler für ungültige Parameter aufgerufen, wie in beschrieben [ Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **EINVAL**.

### <a name="error-conditions"></a>Fehlerbedingungen

|*pReturnValue*|*timeZoneName*|*sizeInBytes*|*index*|Rückgabewert|Inhalt der *TimeZoneName*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|Größe des ZZ-Namens|**NULL**|0|0 oder 1|0|nicht geändert|
|Größe des ZZ-Namens|any|> 0|0 oder 1|0|ZZ-Name|
|nicht geändert|**NULL**|> 0|any|**EINVAL**|nicht geändert|
|nicht geändert|any|Null|any|**EINVAL**|nicht geändert|
|nicht geändert|any|> 0|> 1|**EINVAL**|nicht geändert|

## <a name="remarks"></a>Hinweise

Die **_get_tzname** Funktion ruft die Darstellung der Zeichenfolge des Namens der aktuellen Zeitzone oder der Standard Sommerzeitzone (DST) in die Adresse von *TimeZoneName* je die Index-Wert zusammen mit der Größe der Zeichenfolge in *pReturnValue*. Wenn *TimeZoneName* ist **NULL** und *SizeInBytes* ist 0 (null), die Größe der Zeichenfolge erforderlich, um die angegebene Zeitzone aufzunehmen, und ein abschließendes Nullzeichen in Bytes im zurückgegeben*pReturnValue*. Die Indexwerte müssen entweder für Standard-Zeitzonen 0 oder 1 für Standard-Zeitzone Sommerzeit werden; Alle anderen Werte von *Index* haben unbestimmte Ergebnisse.

## <a name="example"></a>Beispiel

In diesem Beispiel ruft **_get_tzname** abzurufenden die erforderliche Puffergröße zum Anzeigen der aktuellen Standard Sommerzeitzone, weist Sie einen Puffer dieser Größe, Aufrufe **_get_tzname** erneut aus, um den Namen im Laden der gepuffert, und gibt sie an der Konsole.

```C
// crt_get_tzname.c
// Compile by using: cl /W4 crt_get_tzname.c
#include <stdio.h>
#include <time.h>
#include <malloc.h>

enum TZINDEX {
    STD,
    DST
};

int main()
{
    size_t tznameSize = 0;
    char * tznameBuffer = NULL;

    // Get the size of buffer required to hold DST time zone name
    if (_get_tzname(&tznameSize, NULL, 0, DST))
        return 1;    // Return an error value if it failed

    // Allocate a buffer for the name
    if (NULL == (tznameBuffer = (char *)(malloc(tznameSize))))
        return 2;    // Return an error value if it failed

    // Load the name in the buffer
    if (_get_tzname(&tznameSize, tznameBuffer, tznameSize, DST))
        return 3;    // Return an error value if it failed

    printf_s("The current Daylight standard time zone name is %s.\n", tznameBuffer);
    return 0;
}
```

### <a name="output"></a>Output

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

Weitere Informationen finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Uhrzeitverwaltung](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
