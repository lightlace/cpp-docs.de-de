---
title: _ecvt_s
ms.date: 04/05/2018
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
ms.openlocfilehash: 0123c618eb5ba614bd8e5b5b3f1f4b0aff539c4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435580"
---
# <a name="ecvts"></a>_ecvt_s

Konvertiert eine **doppelte** -Zahl in eine Zeichenfolge. Dies ist eine sicherere Version von [_ecvt](ecvt.md), wie unter [Security Features in the CRT (Sicherheitsfunktionen in der CRT)](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

## <a name="syntax"></a>Syntax

```C
errno_t _ecvt_s(
   char * _Buffer,
   size_t _SizeInBytes,
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
);
template <size_t size>
errno_t _ecvt_s(
   char (&_Buffer)[size],
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
); // C++ only
```

### <a name="parameters"></a>Parameter

*_Buffer*<br/>
Wird mit dem Zeiger auf die Zeichenfolge mit Ziffern aufgefüllt, die sich aus der Konvertierung ergeben.

*_SizeInBytes*<br/>
Größe des Puffers in Byte.

*"_Value"*<br/>
Zu konvertierende Zahl.

*_Count*<br/>
Anzahl der gespeicherten Ziffern.

*_Dec*<br/>
Gespeicherte Position der Dezimalstelle.

*_Signieren*<br/>
Vorzeichen der konvertierten Zahl.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich. Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt. Fehlercodes sind in Errno.h definiert. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bei einem in der folgenden Tabelle enthaltenen ungültigen Parameter wird von dieser Funktion der Handler für ungültige Parameter aufgerufen, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **EINVAL**.

### <a name="error-conditions"></a>Fehlerbedingungen

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|Rückgabewert|Wert in *Puffer*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**NULL**|any|any|any|any|any|**EINVAL**|Nicht geändert.|
|Nicht **NULL** (zeigt auf gültigen Speicher)|<=0|any|any|any|any|**EINVAL**|Nicht geändert.|
|any|any|any|any|**NULL**|any|**EINVAL**|Nicht geändert.|
|any|any|any|any|any|**NULL**|**EINVAL**|Nicht geändert.|

## <a name="security-issues"></a>Sicherheitsprobleme

**_ecvt_s** kann eine zugriffsverletzung erzeugen, wenn *Puffer* nicht auf gültigen Speicher verweist und nicht **NULL**.

## <a name="remarks"></a>Hinweise

Die **_ecvt_s** -Funktion konvertiert eine Gleitkommazahl in eine Zeichenfolge. Die *"_value"* -Parameter ist die zu konvertierende Gleitkommazahl. Diese Funktion speichert bis zu *Anzahl* Ziffern *"_value"* als Zeichenfolge und fügt ein Null-Zeichen ('\0'). Wenn die Anzahl der Ziffern in *"_value"* überschreitet *_Count*, wird die untere Ziffer gerundet. Wenn weniger als *Anzahl* Ziffern, die Zeichenfolge mit Nullen aufgefüllt.

In der Zeichenfolge werden nur Ziffern gespeichert. Die Position der Dezimalstelle und das Vorzeichen des *"_value"* erhalten *_Dec* und *_signieren* nach dem Aufruf. Die *_Dec* Parameter verweist auf einen ganzzahligen Wert, der die Position der Dezimalstelle im Verhältnis der Anfang der Zeichenfolge. Der Wert 0 oder ein negativer Integer-Wert geben an, dass sich die Dezimalstelle links neben der ersten Ziffer befindet. Die *_signieren* Parameter verweist auf eine ganze Zahl, die das Vorzeichen der konvertierten Zahl angibt. Wenn der Integer-Wert 0 ist, ist die Zahl positiv. Andernfalls ist die Zahl negativ.

Ein Puffer der Länge **_CVTBUFSIZE** reicht für alle Gleitkommawerte.

Der Unterschied zwischen **_ecvt_s** und **_fcvt_s** befindet sich in die Interpretation der *_Count* Parameter. **_ecvt_s** interpretiert *_Count* als die Gesamtanzahl von Ziffern in der Ausgabezeichenfolge während **_fcvt_s** interpretiert *_Count* als die Anzahl der Ziffern nach dem dem Dezimaltrennzeichen an.

Die Verwendung dieser Funktion in C++ wird durch eine Vorlagenüberladung vereinfacht. Eine Überladung kann automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversion dieser Funktion füllt zunächst den Puffer mit „0xFD“ auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|Optionaler Header|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// ecvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( )
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_ecvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 12000
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
