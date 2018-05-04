---
title: _ecvt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ecvt
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
- _ecvt
dev_langs:
- C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 302cfae33e1567c2dc94c73156df005fcbb667f4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ecvt"></a>_ecvt

Konvertiert eine **doppelte** -Zahl in eine Zeichenfolge. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_ecvt_s](ecvt-s.md).

## <a name="syntax"></a>Syntax

```C
char *_ecvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Zu konvertierende Zahl.

*count*<br/>
Anzahl der gespeicherten Ziffern.

*dec*<br/>
Gespeicherte Position der Dezimalstelle.

*sign*<br/>
Vorzeichen der konvertierten Zahl.

## <a name="return-value"></a>Rückgabewert

**_ecvt** gibt einen Zeiger auf die Zeichenfolge von Ziffern; NULL, wenn ein Fehler aufgetreten.

## <a name="remarks"></a>Hinweise

Die **_ecvt** -Funktion konvertiert eine Gleitkommazahl in eine Zeichenfolge. Die *Wert* Parameter ist die Gleitkommazahl konvertiert werden. Diese Funktion speichert bis zu *Anzahl* Ziffern *Wert* als Zeichenfolge und fügt ein Null-Zeichen ('\0'). Wenn die Anzahl der Ziffern in *Wert* überschreitet *Anzahl*, die niedrige Ziffer gerundet wird. Wenn weniger als *Anzahl* Ziffern, die Zeichenfolge wird mit Nullen aufgefüllt.

Die Gesamtanzahl der Ziffern zurückgegebenes **_ecvt** nicht überschritten **_CVTBUFSIZE**.

In der Zeichenfolge werden nur Ziffern gespeichert. Die Position des Dezimaltrennzeichen und das Vorzeichen des *Wert* abgerufen werden kann, aus *Dec* und *Anmeldung* nach dem Aufruf. Die *Dec* Parameter verweist auf einen ganzzahligen Wert, wodurch die Position neben dem Dezimalzeichen in Bezug auf den Anfang der Zeichenfolge. Der Wert 0 oder ein negativer Integer-Wert geben an, dass sich die Dezimalstelle links neben der ersten Ziffer befindet. Die *Anmeldung* Parameter verweist auf eine ganze Zahl, die das Vorzeichen der konvertierte Zahl angibt. Wenn der Integer-Wert 0 ist, ist die Zahl positiv. Andernfalls ist die Zahl negativ.

Der Unterschied zwischen **_ecvt** und **_fcvt** befindet sich in der Interpretation der *Anzahl* Parameter. **_ecvt** interpretiert *Anzahl* als die Gesamtzahl der Ziffern in der Ausgabezeichenfolge während **_fcvt** interpretiert *Anzahl* als die Anzahl der Ziffern nach dem Dezimaltrennzeichen.

**_ecvt** und **_fcvt** verwenden Sie einen einzelnen statisch zugeordneten Puffer für die Konvertierung. Bei jedem Aufruf dieser Routinen wird das Ergebnis des vorherigen Aufrufs zerstört.

Diese Funktion überprüft ihre Parameter. Wenn *Dec* oder *Anmeldung* NULL ist, oder *Anzahl* gleich 0 ist, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und NULL zurückgegeben.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_ecvt.c
// compile with: /W3
// This program uses _ecvt to convert a
// floating-point number to a character string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int     decimal,   sign;
   char    *buffer;
   int     precision = 10;
   double  source = 3.1415926535;

   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996
   // Note: _ecvt is deprecated; consider using _ecvt_s instead
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",
           source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
