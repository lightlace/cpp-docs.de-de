---
title: atof, _atof_l, _wtof, _wtof_l
ms.date: 04/05/2018
apiname:
- _wtof_l
- atof
- _atof_l
- _wtof
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
- _tstof
- _ttof
- atof
- stdlib/atof
- math/atof
- _atof_l
- stdlib/_atof_l
- math/_atof_l
- _wtof
- corecrt_wstdlib/_wtof
- _wtof_l
- corecrt_wstdlib/_wtof_l
helpviewer_keywords:
- tstof function
- atof_l function
- _atof_l function
- atof function
- _tstof function
- _ttof function
- wtof function
- _wtof_l function
- ttof function
- wtof_l function
- _wtof function
- string conversion, to floating point values
ms.assetid: eb513241-c9a9-4f5c-b7e7-a49b14abfb75
ms.openlocfilehash: 6c2ec158ac0b75a861b5b226d33de113d76988cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471174"
---
# <a name="atof-atofl-wtof-wtofl"></a>atof, _atof_l, _wtof, _wtof_l

Konvertieren einer Zeichenfolge in einen Wert mit doppelter Genauigkeit.

## <a name="syntax"></a>Syntax

```C
double atof(
   const char *str
);
double _atof_l(
   const char *str,
   _locale_t locale
);
double _wtof(
   const wchar_t *str
);
double _wtof_l(
   const wchar_t *str,
   _locale_t locale
);
```

## <a name="parameters"></a>Parameter

*str*<br/>
Zu konvertierende Zeichenfolge.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede Funktion gibt die **doppelte** Wert erzeugt, indem die Eingabezeichen als Zahl interpretiert. Der Rückgabewert ist 0,0, wenn die Eingabe nicht in einen Wert dieses Typs umgewandelt werden kann.

In allen Fällen außerhalb des gültigen Bereichs **Errno** nastaven NA hodnotu **ERANGE**. Wenn der übergebene Parameter ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL** und gibt 0 zurück.

## <a name="remarks"></a>Hinweise

Diese Funktionen konvertieren eine Zeichenfolge in einen Gleitkommawert mit doppelter Genauigkeit.

Die Eingabezeichenfolge ist eine Sequenz von Zeichen, die als numerischer Wert des angegebenen Typs interpretiert werden. Die Funktion beendet das Lesen der Eingabezeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird. Möglicherweise ist dies das Zeichen NULL ('\0' oder L'\0'), das am Ende der Zeichenfolge steht.

Die *str* Argument **Atof** und **_wtof** hat folgendes Format:

[*Leerzeichen*] [*anmelden*] [*Ziffern*] [__.__ *Ziffern*] [{**e** &#124; **E** } [*anmelden*]*Ziffern*]

Ein *Leerzeichen* besteht aus Leerzeichen oder Tabulatorzeichen, die ignoriert werden; *anmelden* ist entweder Pluszeichen (+) oder Minuszeichen (-) und *Ziffern* sind eine oder mehrere Dezimalstellen. Wenn keine Ziffern vor dem Dezimaltrennzeichen stehen, muss mindestens eine Ziffer nach dem Dezimaltrennzeichen stehen. Die Dezimalstellen folgt möglicherweise ein Exponent, der besteht aus einem einführenden Buchstaben (**e**, oder **E**) und einer optionalen ganzen Dezimalzahl.

Die UCRT-Versionen dieser Funktionen unterstützen keine Konvertierung von Fortran-Stil (**d** oder **D**) Buchstaben in Exponenten. Diese nicht-standardmäßige Erweiterung wurde in früheren Versionen der CRT unterstützt. Sie ist möglicherweise eine fehlerhafte Änderung für Ihren Code.

Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie verwenden die *Gebietsschema* übergebene Parameter anstelle des aktuellen Gebietsschemas.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstof**|**atof**|**atof**|**_wtof**|
|**_ttof**|**atof**|**atof**|**_wtof**|

## <a name="requirements"></a>Anforderungen

|Routine(n)|Erforderlicher Header|
|------------------|---------------------|
|**Atof**, **_atof_l**|C: \<math.h> or \<stdlib.h> C++: \<cstdlib>, \<stdlib.h>, \<cmath> or \<math.h>|
|**_wtof**, **_wtof_l**|C: \<stdlib.h> oder \<wchar.h> C++: \<cstdlib>, \<stdlib.h> oder \<wchar.h>|

## <a name="example"></a>Beispiel

Dieses Programm zeigt, wie als Zeichenfolgen gespeicherte Zahlen in numerische Werte konvertiert werden können die **Atof** und **_atof_l** Funktionen.

```C
// crt_atof.c
//
// This program shows how numbers stored as
// strings can be converted to numeric
// values using the atof and _atof_l functions.

#include <stdlib.h>
#include <stdio.h>
#include <locale.h>

int main(void)
{
    char    *str = NULL;
    double value = 0;
    _locale_t fr = _create_locale(LC_NUMERIC, "fr-FR");

    // An example of the atof function
    // using leading and training spaces.
    str = "  3336402735171707160320 ";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);

    // Another example of the atof function
    // using the 'E' exponential formatting keyword.
    str = "3.1412764583E210";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);

    // An example of the atof and _atof_l functions
    // using the 'e' exponential formatting keyword
    // and showing different decimal point interpretations.
    str = "  -2,309e-25";
    value = atof(str);
    printf("Function: atof(\"%s\") = %e\n", str, value);
    value = _atof_l(str, fr);
    printf("Function: _atof_l(\"%s\", fr)) = %e\n", str, value);
}
```

```Output
Function: atof("  3336402735171707160320 ") = 3.336403e+21
Function: atof("3.1412764583E210") = 3.141276e+210
Function: atof("  -2,309e-25") = -2.000000e+00
Function: _atof_l("  -2,309e-25", fr)) = -2.309000e-25
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
