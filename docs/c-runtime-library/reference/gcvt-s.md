---
title: _gcvt_s
ms.date: 04/05/2018
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
ms.openlocfilehash: 168e0657150d072bbe41cd0ad6e914ca1f53e512
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554961"
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
|**NULL**|any|any|any|**EINVAL**|Nicht geändert.|
|Nicht **NULL** (zeigt auf gültigen Speicher)|Null|any|any|**EINVAL**|Nicht geändert.|
|Nicht **NULL** (zeigt auf gültigen Speicher)|any|any|>= *sizeInBytes*|**EINVAL**|Nicht geändert.|

**Sicherheitsprobleme**

**_gcvt_s** kann eine zugriffsverletzung erzeugen, wenn *Puffer* nicht auf gültigen Speicher verweist und nicht **NULL**.

## <a name="remarks"></a>Hinweise

Die **_gcvt_s** Funktion konvertiert ein Gleitkomma *Wert* in eine Zeichenfolge (enthält Dezimaltrennzeichen und einem möglichen Zeichen-Byte) und speichert die Zeichenfolge in *Puffer* . *Puffer* muss groß genug für den konvertierten Wert und ein abschließendes Nullzeichen, das automatisch angefügt wird. Ein Puffer der Länge **_CVTBUFSIZE** reicht für alle Gleitkommawerte Wert. Wenn eine Puffergröße *Ziffern* + 1 verwendet wird, wird die Funktion überschreibt nicht das Ende des Puffers, daher unbedingt einen ausreichenden Puffer für diesen Vorgang übergeben. **_gcvt_s** versucht, erzeugen *Ziffern* -Ziffern im Dezimalformat. Wenn dies nicht möglich ist, erzeugt es *Ziffern* -Ziffern im Exponentialformat. Bei der Konvertierung können Nachstellen von Nullen unterdrückt werden.

Die Verwendung dieser Funktion in C++ wird durch eine Überladung (als Vorlagen vorhanden) vereinfacht. Eine Überladung kann automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversion dieser Funktion füllt zunächst den Puffer mit „0xFD“ auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
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
