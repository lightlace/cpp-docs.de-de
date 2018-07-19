---
title: _gcvt_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _gcvt_s
- gcvt_s
dev_langs:
- C++
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a2bd12a63db064bca0c880484f99a2df9d210f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403767"
---
# <a name="gcvts"></a>_gcvt_s

Konvertiert einen Gleitkommawert in eine Zeichenfolge. Dies ist eine sicherere Version von [_gcvt](gcvt.md), wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

## <a name="syntax"></a>Syntax

```C
errno_t _gcvt_s(
   char *buffer,
   size_t sizeInBytes,
   double value,
   int digits
);
template <size_t cchStr>
errno_t _gcvt_s(
   char (&buffer)[cchStr],
   double value,
   int digits
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Puffer, um das Ergebnis der Konvertierung zu speichern

*sizeInBytes*<br/>
Größe des Puffers.

*Wert*<br/>
Zu konvertierender Wert.

*Ziffern*<br/>
Anzahl der gespeicherten signifikanten Ziffern.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich. Tritt ein Fehler aufgrund eines ungültigen Parameters auf (siehe folgende Tabelle für ungültige Werte), wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md)beschrieben wird. Wenn die weitere Ausführung zugelassen wird, wird ein Fehlercode zurückgegeben. Fehlercodes sind in Errno.h definiert. Eine Liste dieser Fehler finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Fehlerbedingungen

|*buffer*|*sizeInBytes*|*Wert*|*Ziffern*|Zurück|Wert in *Puffer*|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**NULL**|alle|alle|alle|**EINVAL**|Nicht geändert.|
|Nicht **NULL** (verweist auf gültige Speicher)|Null|alle|alle|**EINVAL**|Nicht geändert.|
|Nicht **NULL** (verweist auf gültige Speicher)|alle|alle|>= *sizeInBytes*|**EINVAL**|Nicht geändert.|

**Sicherheitsprobleme**

**_gcvt_s** kann eine zugriffsverletzung generiert, wenn *Puffer* zeigt nicht auf gültige Speicher und ist nicht **NULL**.

## <a name="remarks"></a>Hinweise

Die **_gcvt_s** -Funktion konvertiert eine Gleitkommazahl *Wert* in eine Zeichenfolge (enthält Dezimaltrennzeichen und ein Byte möglichen Anmeldung) und speichert die Zeichenfolge in *Puffer* . *Puffer* muss groß genug für den konvertierten Wert plus ein abschließendes Nullzeichen, das automatisch angefügt wird. Ein Puffer von Länge **_CVTBUFSIZE** reicht für alle Gleitkommawert Datenpunktwert. Wenn die Größe des Befehlspuffers von *Ziffern* + 1 wird verwendet, die Funktion überschreibt keine am Ende des Puffers, daher unbedingt einen ausreichenden Puffer für diesen Vorgang angeben. **_gcvt_s** erzeugen versucht *Ziffern* Ziffern im Dezimalformat. Wenn es nicht möglich ist, erzeugt es *Ziffern* Ziffern im Exponentialformat. Bei der Konvertierung können Nachstellen von Nullen unterdrückt werden.

Die Verwendung dieser Funktion in C++ wird durch eine Überladung (als Vorlagen vorhanden) vereinfacht. Eine Überladung kann automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversion dieser Funktion füllt zunächst den Puffer mit „0xFD“ auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_gcvt_s**|\<stdlib.h>|\<error.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_gcvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main()
{
    char buf[_CVTBUFSIZE];
    int decimal;
    int sign;
    int err;

    err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);

    if (err != 0)
    {
        printf("_gcvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 1.2
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt](gcvt.md)<br/>
