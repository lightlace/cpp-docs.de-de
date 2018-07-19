---
title: _atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _atoldbl
- _atoldbl_l
- _atodbl
- _atoflt
- _atoflt_l
- _atodbl_l
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
- _atoflt
- _atoflt_l
- atodbl_l
- atoflt_l
- _atoldbl
- _atoldbl_l
- atodbl
- _atodbl_l
- atoldbl
- atoflt
- atoldbl_l
- _atodbl
dev_langs:
- C++
helpviewer_keywords:
- _atodbl function
- _atoldbl_l function
- atoflt function
- atoflt_l function
- atoldbl function
- _atoldbl function
- atodbl_l function
- _atoflt_l function
- atoldbl_l function
- atodbl function
- string conversion, to floating point values
- _atoflt function
- _atodbl_l function
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da36dfae81f33f5fb30a1a4bc93a57437980d720
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393588"
---
# <a name="atodbl-atodbll-atoldbl-atoldbll-atoflt-atofltl"></a>_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l

Konvertiert eine Zeichenfolge in einen Double (**_atodbl**), long double (**_atoldbl**), oder "float" (**_atoflt**).

## <a name="syntax"></a>Syntax

```C
int _atodbl( _CRT_DOUBLE * value, char * str );
int _atodbl_l ( _CRT_DOUBLE * value, char * str, locale_t locale );
int _atoldbl( _LDOUBLE * value, char * str );
int _atoldbl_l ( _LDOUBLE * value, char * str, locale_t locale );
int _atoflt( _CRT_FLOAT * value, const char * str );
int _atoflt_l( _CRT_FLOAT * value, const char * str, locale_t locale );
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Der double-, long double- oder float-Wert, der erstellt wird, indem die Zeichenfolge in einen Gleitkommawert konvertiert wird. Diese Werte werden in eine Struktur eingeschlossen.

*str*<br/>
Die zu analysierende Zeichenfolge, die in einen Gleitkommawert konvertiert wird.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg 0 zurück. Mögliche Fehlercodes sind **_UNDERFLOW** oder **_OVERFLOW**, die in der Headerdatei definiert werden \<math.h >.

## <a name="remarks"></a>Hinweise

Diese Funktionen konvertieren eine Zeichenfolge in einen Gleitkommawert. Der Unterschied zwischen diesen Funktionen und die **Atof** Funktionsreihe ist, dass diese Funktionen nicht gleitkommacode generieren und Hardwareausnahmen verursachen. Stattdessen werden Fehlerzustände als Fehlercodes gemeldet.

Wenn eine Zeichenfolge keine gültige Interpretation als Gleitkommawert *Wert* ist auf 0 gesetzt und das zurückgegebene Wert ist 0 (null).

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch die Versionen, die das Suffix haben, verwenden jedoch den *Gebietsschema* übergebenen Gebietsschemaparameter anstelle des aktuellen Threads Gebietsschema.

## <a name="requirements"></a>Anforderungen

|Routinen|Erforderlicher Header|
|--------------|---------------------|
|**_atodbl**, **_atoldbl**, **_atoflt**<br /><br /> **_atodbl_l**, **_atoldbl_l**, **_atoflt_l**|\<stdlib.h>|

## <a name="example"></a>Beispiel

```C
// crt_atodbl.c
// Uses _atodbl to convert a string to a double precision
// floating point value.

#include <stdlib.h>
#include <stdio.h>

int main()
{
   char str1[256] = "3.141592654";
   char abc[256] = "abc";
   char oflow[256] = "1.0E+5000";
   _CRT_DOUBLE dblval;
   _CRT_FLOAT fltval;
   int retval;

   retval = _atodbl(&dblval, str1);

   printf("Double value: %lf\n", dblval.x);
   printf("Return value: %d\n\n", retval);

   retval = _atoflt(&fltval, str1);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   // A non-floating point value: returns 0.
   retval = _atoflt(&fltval, abc);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   // Overflow.
   retval = _atoflt(&fltval, oflow);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   return 0;
}
```

```Output
Double value: 3.141593
Return value: 0

Float value: 3.141593
Return value: 0

Float value: 0.000000
Return value: 0

Float value: inf
Return value: 3
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
