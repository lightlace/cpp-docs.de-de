---
title: _fcvt
ms.date: 04/05/2018
apiname:
- _fcvt
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
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: ae9323e3bb629fd61b35a8c844b00bfcc73235bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334839"
---
# <a name="fcvt"></a>_fcvt

Konvertiert eine Gleitkommazahl in eine Zeichenfolge. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_fcvt_s](fcvt-s.md).

## <a name="syntax"></a>Syntax

```C
char *_fcvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>Parameter

*value*<br/>
Zu konvertierende Zahl.

*count*<br/>
Anzahl der Ziffern nach dem Dezimaltrennzeichen.

*dec*<br/>
Zeiger auf die gespeicherte Position der Dezimalstelle.

*sign*<br/>
Zeiger auf den gespeicherten Zeichen-Indikator.

## <a name="return-value"></a>Rückgabewert

**_fcvt** gibt einen Zeiger zur Zeichenfolge der Ziffern **NULL** bei einem Fehler.

## <a name="remarks"></a>Hinweise

Die **_fcvt** -Funktion konvertiert eine Gleitkommazahl in eine Null-terminierte Zeichenfolge. Die *Wert* -Parameter ist die zu konvertierende Gleitkommazahl. **_fcvt** speichert die Ziffern von *Wert* als Zeichenfolge und fügt ein Null-Zeichen ('\0'). Die *Anzahl* Parameter gibt die Anzahl der Ziffern nach dem Dezimaltrennzeichen gespeichert werden. Überschüssige Ziffern werden gerundet, *Anzahl* platziert. Wenn weniger als *Anzahl* Dezimalstellen, die Zeichenfolge mit Nullen aufgefüllt.

Die Gesamtanzahl der Ziffern, die vom **_fcvt** werden nicht mehr als **_CVTBUFSIZE**.

In der Zeichenfolge werden nur Ziffern gespeichert. Die Position der Dezimalstelle und das Vorzeichen des *Wert* erhalten *Dec* und melden Sie nach dem Aufruf. Die *Dec* Parameter verweist auf einen ganzzahligen Wert; dieser ganzzahlige Wert gibt die Position der Dezimalstelle im Verhältnis der Anfang der Zeichenfolge. Der Wert null oder ein negativer ganzzahliger Wert geben an, dass sich die Dezimalstelle links neben der ersten Ziffer befindet. Der Parameter *anmelden* verweist auf eine ganze Zahl, der das Vorzeichen *Wert*. Die ganze Zahl auf 0 festgelegt ist, wenn *Wert* positiv ausfällt und wird festgelegt, auf eine Zahl ungleich NULL, wenn *Wert* ist negativ.

Der Unterschied zwischen **_ecvt** und **_fcvt** befindet sich in die Interpretation der *Anzahl* Parameter. **_ecvt** interpretiert *Anzahl* als die Gesamtanzahl von Ziffern in der Ausgabezeichenfolge während **_fcvt** interpretiert *Anzahl* als die Anzahl der Ziffern nach dem Dezimaltrennzeichen an.

**_ecvt** und **_fcvt** verwenden einen einzelnen statisch zugewiesenen Puffer für die Konvertierung. Jeder Aufruf einer dieser Routinen zerstört das Ergebnis des vorherigen Aufrufs.

Diese Funktion überprüft ihre Parameter. Wenn *Dec* oder *anmelden* ist **NULL**, oder *Anzahl* gleich 0 ist, den Handler für ungültige Parameter aufgerufen, siehe [Parameter Überprüfung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und **NULL** zurückgegeben wird.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fcvt.c
// compile with: /W3
// This program converts the constant
// 3.1415926535 to a string and sets the pointer
// buffer to point to that string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int  decimal, sign;
   char *buffer;
   double source = 3.1415926535;

   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996
   // Note: _fcvt is deprecated; consider using _fcvt_s instead
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",
            source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
