---
title: _create_locale, _wcreate_locale
ms.date: 11/04/2016
api_name:
- _create_locale
- __create_locale
- _wcreate_locale
api_location:
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
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- create_locale
- _create_locale
- __create_locale
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
ms.openlocfilehash: a7098dc572ecdbefd891efc8443e977b01850fa4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938856"
---
# <a name="_create_locale-_wcreate_locale"></a>_create_locale, _wcreate_locale

Erstellt ein locale-Objekt.

## <a name="syntax"></a>Syntax

```C
_locale_t _create_locale(
   int category,
   const char *locale
);
_locale_t _wcreate_locale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Parameter

*category*<br/>
Kategorie.

*locale*<br/>
Gebietsschemaspezifizierer.

## <a name="return-value"></a>Rückgabewert

Wenn *ein gültiges Gebiets* Schema und eine gültige *Kategorie* angegeben werden, gibt die angegebenen Gebiets Schema Einstellungen als **_locale_t** -Objekt zurück. Die aktuellen Gebietsschemaeinstellungen des Programms werden nicht geändert.

## <a name="remarks"></a>Hinweise

Mit der **_create_locale** -Funktion können Sie ein Objekt erstellen, das bestimmte regionsspezifische Einstellungen darstellt, die in Gebiets Schema spezifischen Versionen vieler CRT-Funktionen (Funktionen mit dem **_l** -Suffix) verwendet werden können. Das Verhalten ähnelt **setlocale**, mit dem Unterschied, dass die Einstellungen in einer **_locale_t** -Struktur gespeichert werden, die zurückgegeben wird, anstatt die angegebenen Gebiets Schema Einstellungen auf die aktuelle Umgebung anzuwenden. Die **_locale_t** -Struktur sollte mithilfe von [_free_locale](free-locale.md) freigegeben werden, wenn Sie nicht mehr benötigt wird.

**_wcreate_locale** ist eine breit Zeichen Version von **_create_locale**. Das *Gebiets* Schema Argument für **_wcreate_locale** ist eine Zeichenfolge mit breit Zeichen. **_wcreate_locale** und **_create_locale** Verhalten sich andernfalls identisch.

Das *Category* -Argument gibt die Teile des Gebiets Schema spezifischen Verhaltens an, die betroffen sind. Die für die *Kategorie* verwendeten Flags und die betroffenen Teile des Programms sind wie in dieser Tabelle dargestellt:

| *kategorieflag* | Betrifft |
|-----------------|---------|
| **LC_ALL** |Alle unten aufgeführten Kategorien. |
| **LC_COLLATE** |Die Funktionen "", "_stricoll", " **wcscoll**", " **_wcsicoll** **", "** **", "** **_strncoll**", " **_strnicoll**", " **_wcsncoll**", " **_wcsnicoll**" und " **wcsxfrm** |
| **LC_CTYPE** | Die Funktionen zur Zeichen Behandlung (außer **IsDigit**, **isxdigit**, **mbstowcs**und **mbtowc**, die nicht betroffen sind). |
| **LC_MONETARY** | Informationen zur monetären Formatierung, die von der **localeconv** -Funktion zurückgegeben werden. |
| **LC_NUMERIC** | Ein Dezimaltrennzeichen für die formatierten Ausgaberoutinen (z. **b. printf**), für die Daten Konvertierungs Routinen und für die nicht monetären Formatierungsinformationen, die von **localeconv**zurückgegeben werden. Neben dem Dezimaltrennzeichen legt **LC_NUMERIC** das Tausender Trennzeichen und die Zeichenfolge für die Gruppierungs Steuerung fest, die von [localeconv](localeconv.md)zurückgegeben wurde. |
| **LC_TIME** | Die Funktionen " **Strauch Zeit** " und " **WCSF Time** ". |

Diese Funktion überprüft die *Kategorieparameter* *und Gebiets* Schema Parameter. Wenn der Category-Parameter keinem der in der vorherigen Tabelle angegebenen *Werte entspricht oder* das Gebiets Schema **null**ist, gibt die Funktion **null**zurück.

Das *locale* -Argument ist ein Zeiger auf eine Zeichenfolge, die das Gebiets Schema angibt. Weitere Informationen zum *Format des Gebiets Schema Arguments finden* Sie unter Gebiets Schema [Namen, Sprachen und Länder-](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)/regionszeichenfolgen.

Das *locale* -Argument kann einen Gebiets Schema Namen, eine Sprachen Zeichenfolge, eine Sprachen Zeichenfolge und Länder-/Regionscode, eine Codepage oder eine Sprachen Zeichenfolge, einen Länder-/Regionscode und eine Codepage annehmen. Der Satz verfügbarer Gebietsschemanamen, Sprachen, Länder-/Regionscodes und Codepages umfasst alle diejenigen, die von der Windows NLS-API unterstützt werden, ausgenommen Codepages, die mehr als zwei Bytes pro Zeichen benötigen, wie z. B. UTF-7 und UTF-8. Wenn Sie eine Codepage wie UTF-7 oder UTF-8 bereitstellen, schlägt **_create_locale** fehl und gibt **null**zurück. Der von **_create_locale** unterstützte Satz von Gebiets Schema Namen wird in Gebiets Schema [Namen, Sprachen und Zeichen folgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)beschrieben. Die von **_create_locale** unterstützten sprach-und Länder-/regionszeichenfolgen werden in [sprach](../../c-runtime-library/language-strings.md) Zeichenfolgen und Zeichen folgen für [Länder/Regionen](../../c-runtime-library/country-region-strings.md)aufgeführt.

Weitere Informationen zu Gebietsschemaeinstellungen finden Sie unter [setlocale, _wsetlocale](setlocale-wsetlocale.md).

Der vorherige Name dieser Funktion, **__create_locale** (mit zwei führenden unterstrichen), ist veraltet.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_create_locale**|\<locale.h>|
|**_wcreate_locale**|\<locale.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_create_locale.c
// Sets the current locale to "de-CH" using the
// setlocale function and demonstrates its effect on the strftime
// function.

#include <stdio.h>
#include <locale.h>
#include <time.h>

int main(void)
{
    time_t ltime;
    struct tm thetime;
    unsigned char str[100];
    _locale_t locale;

    // Create a locale object representing the German (Switzerland) locale
    locale = _create_locale(LC_ALL, "de-CH");
    time (&ltime);
    _gmtime64_s(&thetime, &ltime);

    // %#x is the long date representation, appropriate to
    // the current locale
    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);

    // Create a locale object representing the default C locale
    locale = _create_locale(LC_ALL, "C");
    time(&ltime);
    _gmtime64_s(&thetime, &ltime);

    if (!_strftime_l((char *)str, 100, "%#x",
                     (const struct tm *)&thetime, locale))
    {
        printf("_strftime_l failed!\n");
    }
    else
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);
    }

    _free_locale(locale);
}
```

```Output
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'
```

## <a name="see-also"></a>Siehe auch

[Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Language Strings](../../c-runtime-library/language-strings.md)<br/>
[Country/Region Strings](../../c-runtime-library/country-region-strings.md)<br/>
[_free_locale](free-locale.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
