---
title: _create_locale _wcreate_locale | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _create_locale
- __create_locale
- _wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- create_locale
- _create_locale
- __create_locale
dev_langs:
- C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db4a762689907330b671e2720cf743ee957526a4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="createlocale-wcreatelocale"></a>_create_locale, _wcreate_locale

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

Wenn Sie eine gültige *Gebietsschema* und *Kategorie* angegeben sind, gibt die angegebenen gebietsschemaeinstellungen als eine **_locale_t** Objekt. Die aktuellen Gebietsschemaeinstellungen des Programms werden nicht geändert.

## <a name="remarks"></a>Hinweise

Die **_create_locale** Funktion ermöglicht Ihnen die Erstellung ein Objekts, das bestimmte bereichsspezifische Einstellungen, für die Verwendung in gebietsschemaspezifischen Versionen vieler CRT-Funktionen darstellt (Funktionen mit dem **_l** Suffix ). Das Verhalten ähnelt **Setlocale**, außer dass anstatt die angegebenen gebietsschemaeinstellungen auf der aktuellen Umgebung anwenden, die Einstellungen, in gespeichert werden einem **_locale_t** -Struktur, die zurückgegeben wird. Die **_locale_t** Struktur Verwendung freigegeben werden sollten [_free_locale](free-locale.md) wenn er nicht mehr benötigt.

**_wcreate_locale** ist eine Breitzeichen-Version von **_create_locale**; das *Gebietsschema* Argument **_wcreate_locale** ist eine Breitzeichen-Zeichenfolge. **_wcreate_locale** und **_create_locale** Verhalten sich andernfalls identisch.

Die *Kategorie* Argument gibt die betroffenen Teile des gebietsschemaspezifischen Verhaltens an. Die Flags, die zum *Kategorie* und die Teile des Programms sind, wie in der folgenden Tabelle gezeigt.

|*Kategorie* Flag|Betrifft|
|-|-|
**LC_ALL**|Alle unten aufgeführten Kategorien.
**LC_COLLATE**|Die **Strcoll**, **_stricoll**, **Wcscoll**, **_wcsicoll**, **Strxfrm**, **_ Strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, und **Wcsxfrm** Funktionen.
**LC_CTYPE**|Die Funktionen zur Verarbeitung von Zeichen (mit Ausnahme von **Isdigit**, **Isxdigit**, **Mbstowcs**, und **Mbtowc**, die nicht betroffen sind).
**LC_MONETARY**|Währungsformatierung Informationen zurückgegeben werden, indem Sie die **Localeconv** Funktion.
**LC_NUMERIC**|Dezimaltrennzeichen für die formatierten ausgaberoutinen (wie z. B. **Printf**), für die datenkonvertierungsroutinen und für die nicht monetären Formatierungsinformationen zurückgegebenes **Localeconv**. Neben dem Dezimaltrennzeichen **LC_NUMERIC** legt das Tausendertrennzeichen und die Steuerung von zurückgegebene Zeichenfolge [Localeconv](localeconv.md).
**LC_TIME**|Die **Strftime** und **Wcsftime** Funktionen.

Diese Funktion überprüft der *Kategorie* und *Gebietsschema* Parameter. Wenn der Category-Parameter nicht einen der Werte in der vorherigen Tabelle aufgeführt ist, oder wenn *Gebietsschema* ist **NULL**, gibt die Funktion **NULL**.

Die *Gebietsschema* Argument ist ein Zeiger auf eine Zeichenfolge, die das Gebietsschema angibt. Informationen zum Format von der *Gebietsschema* Argument, finden Sie unter [Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).

Die *Gebietsschema* Argument kann einen Gebietsschemanamen, eine Sprachenzeichenfolge, eine Sprachenzeichenfolge und Länder-/Regionscode, eine Codepage oder eine Sprachenzeichenfolge, Länder-/Regionscode und Codepage zu verwenden. Der Satz verfügbarer Gebietsschemanamen, Sprachen, Länder-/Regionscodes und Codepages umfasst alle diejenigen, die von der Windows NLS-API unterstützt werden, ausgenommen Codepages, die mehr als zwei Bytes pro Zeichen benötigen, wie z. B. UTF-7 und UTF-8. Wenn Sie eine Codepage wie UTF-7 oder UTF-8 bereitstellen **_create_locale** fehlschlagen und NULL zurückgegeben. Die Anzahl von unterstützten Gebietsschemanamen **_create_locale** in beschriebenen [Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Der Satz von Sprache und Land/Region-Zeichenfolgen, die von unterstützt **_create_locale** in aufgelisteten [Sprachenzeichenfolgen](../../c-runtime-library/language-strings.md) und [Länder-/Regionszeichenfolgen](../../c-runtime-library/country-region-strings.md).

Weitere Informationen zu Gebietsschemaeinstellungen finden Sie unter [setlocale, _wsetlocale](setlocale-wsetlocale.md).

Der vorherige Name dieser Funktion **__create_locale** (mit zwei führenden unterstrichen), ist veraltet.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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

[Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Language Strings](../../c-runtime-library/language-strings.md)<br/>
[Länder-/Regionszeichenfolgen](../../c-runtime-library/country-region-strings.md)<br/>
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
