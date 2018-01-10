---
title: _create_locale _wcreate_locale | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 73e89121dda53300b276b76f49625ad274df4519
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="createlocale-wcreatelocale"></a>_create_locale, _wcreate_locale
Erstellt ein locale-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
_locale_t _create_locale(  
   int category,  
   const char *locale   
);  
_locale_t _wcreate_locale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `category`  
 Kategorie.  
  
 `locale`  
 Gebietsschemaspezifizierer.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn gültige `locale`- und `category`-Parameter angegeben sind, werden die angegebenen Gebietsschemaeinstellungen als `_locale_t`-Objekt zurückgegeben. Die aktuellen Gebietsschemaeinstellungen des Programms werden nicht geändert.  
  
## <a name="remarks"></a>Hinweise  
 Die `_create_locale`-Funktion ermöglicht das Erstellen eines Objekts, das bestimmte bereichsspezifische Einstellungen darstellt, die in gebietsschemaspezifischen Versionen vieler CRT-Funktionen (Funktionen mit dem Suffix `_l`) verwendet werden können. Das Verhalten ähnelt `setlocale`, mit dem Unterschied, dass die angegebenen Gebietsschemaeinstellungen nicht auf die aktuelle Umgebung angewendet werden, sondern in einer `_locale_t`-Struktur gespeichert werden, die zurückgegeben wird. Die `_locale_t`-Struktur sollte mit [_free_locale](../../c-runtime-library/reference/free-locale.md) freigestellt werden, wenn sie nicht mehr benötigt wird.  
  
 `_wcreate_locale` ist eine Breitzeichenversion von `_create_locale`. Das `locale`-Argument für `_wcreate_locale` ist eine Breitzeichenfolge. `_wcreate_locale` und `_create_locale` verhalten sich andernfalls identisch.  
  
 Das `category`-Argument gibt die betroffenen Teile des gebietsschemaspezifischen Verhaltens an. Die für `category` verwendeten Flags und die betroffenen Teile des Programms sind in der folgenden Tabelle dargestellt.  
  
 `LC_ALL`  
 Alle unten aufgeführten Kategorien.  
  
 `LC_COLLATE`  
 Die Funktionen `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` und `wcsxfrm`.  
  
 `LC_CTYPE`  
 Die Funktionen zur Zeichenbehandlung (außer `isdigit`, `isxdigit`, `mbstowcs` und `mbtowc`, die nicht betroffen sind).  
  
 `LC_MONETARY`  
 Durch die `localeconv`-Funktion zurückgegebene Informationen zur Währungsformatierung.  
  
 `LC_NUMERIC`  
 Dezimaltrennzeichen für die formatierten Ausgaberoutinen (wie `printf`), für die Datenkonvertierungsroutinen und für die nicht monetären Formatierungsinformationen, die von `localeconv` zurückgegeben werden. Neben dem Dezimaltrennzeichen legt `LC_NUMERIC` das Tausendertrennzeichen und die Zeichenfolge für gruppierte Steuerelemente fest, die von [localeconv](../../c-runtime-library/reference/localeconv.md) zurückgegeben werden.  
  
 `LC_TIME`  
 Die Funktionen `strftime` und `wcsftime`.  
  
 Diese Funktion überprüft den `category`-Parameter und den `locale`-Parameter. Wenn der category-Parameter nicht zu den Werten in der vorherigen Tabelle gehört oder wenn `locale``NULL` ist, gibt die Funktion `NULL` zurück.  
  
 Das `locale`-Argument ist ein Zeiger auf eine Zeichenfolge, die das Gebietsschema angibt. Informationen zum Format des `locale`-Arguments finden Sie unter [Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).  
  
 Das `locale`-Argument kann einen Gebietsschemanamen annehmen, eine Sprachenzeichenfolge, eine Sprachenzeichenfolge und eine Landeskennzahl, eine Codepage oder eine Sprachenzeichenfolge, eine Landeskennzahl eine und Codepage. Der Satz verfügbarer Gebietsschemanamen, Sprachen, Länder-/Regionscodes und Codepages umfasst alle diejenigen, die von der Windows NLS-API unterstützt werden, ausgenommen Codepages, die mehr als zwei Bytes pro Zeichen benötigen, wie z. B. UTF-7 und UTF-8. Wenn Sie eine Codepage wie UTF-7 oder UTF-8 bereitstellen, schlägt `_create_locale` fehl und gibt NULL zurück. Die Gebietsschemanamen, die von `_create_locale` unterstützt werden, wird unter [Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) beschrieben. Der von `_create_locale` unterstützte Satz von Sprach- und Länder-/Regionszeichenfolgen ist in [Sprachzeichenfolgen](../../c-runtime-library/language-strings.md) und [Länder-/Regionszeichenfolgen](../../c-runtime-library/country-region-strings.md) aufgeführt.  
  
 Weitere Informationen zu Gebietsschemaeinstellungen finden Sie unter [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Der vorherige Name dieser Funktion, `__create_locale` (mit zwei führenden Unterstrichen), ist veraltet.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_create_locale`|\<locale.h>|  
|`_wcreate_locale`|\<locale.h> or \<wchar.h>|  
  
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
 [Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Sprachzeichenfolgen](../../c-runtime-library/language-strings.md)   
 [Länder-/Regionszeichenfolgen](../../c-runtime-library/country-region-strings.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)