---
title: _stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l
ms.date: 11/04/2016
apiname:
- _mbsicoll_l
- _stricoll_l
- _mbsicoll
- _wcsicoll_l
- _wcsicoll
- _stricoll
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- stricoll
- _stricoll
- _wcsicoll
- mbsicoll_l
- _mbsicoll
- _ftcsicoll
- wcsicoll_l
- _tcsicoll
- mbsicoll
- stricoll_l
helpviewer_keywords:
- code pages, using for string comparisons
- _ftcsicoll function
- _mbsicoll_l function
- _mbsicoll function
- mbsicoll function
- stricoll function
- tcsicoll function
- string comparison [C++], culture-specific
- _tcsicoll function
- _stricoll function
- _stricoll_l function
- _wcsicoll function
- mbsicoll_l function
- stricoll_l function
- strings [C++], comparing by code page
- ftcsicoll function
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
ms.openlocfilehash: bd2406751fd2855afd02743c98938e530398e7d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353663"
---
# <a name="stricoll-wcsicoll-mbsicoll-stricolll-wcsicolll-mbsicolll"></a>_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l

Vergleicht Zeichenfolgen mithilfe gebietsschemaspezifischen Informationen.

> [!IMPORTANT]
> **_mbsicoll** und **_mbsicoll_l** kann nicht verwendet werden, in Anwendungen, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _stricoll(
   const char *string1,
   const char *string2
);
int _wcsicoll(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicoll(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricoll_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicoll_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*string1*, *string2*<br/>
Zu vergleichende mit NULL endende Zeichenfolgen.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Wert, der angibt, der Beziehung zwischen *string1* zu *Zeichenfolge2*wie folgt.

|Rückgabewert|Verhältnis von string1 zu string2|
|------------------|----------------------------------------|
|< 0|*Zeichenfolge1* kleiner als *Zeichenfolge2*|
|0|*Zeichenfolge1* identisch mit *Zeichenfolge2*|
|> 0|*Zeichenfolge1* größer als *Zeichenfolge2*|
|**_NLSCMPERROR**|Es ist ein Fehler aufgetreten.|

Jede dieser Funktionen gibt **_NLSCMPERROR**. Verwendung von **_NLSCMPERROR**, entweder \<string.h > oder \<mbstring.h >. **_wcsicoll** kann fehlschlagen, wenn *string1* oder *Zeichenfolge2* breitzeichencodes außerhalb der Domäne der Sortierreihenfolge enthält. Wenn ein Fehler auftritt, **_wcsicoll** kann festgelegt **Errno** zu **EINVAL**. Zu prüfen, ein Fehler bei einem Aufruf von **_wcsicoll**legen **Errno** auf 0, und klicken Sie dann überprüfen **Errno** nach dem Aufruf **_wcsicoll**.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen vergleicht Groß-/Kleinschreibung *string1* und *Zeichenfolge2* entsprechend der derzeit verwendeten Codepage. Diese Funktionen sollten nur verwendet werden, wenn es in der aktuellen Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Reihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist.

**_stricmp** unterscheidet sich von **_stricoll** darin, dass die **_stricmp** hat Auswirkungen auf Vergleich von **LC_CTYPE**, während die **_stricoll** -Vergleich den **LC_CTYPE** und **LC_COLLATE** Kategorien des Gebietsschemas. Weitere Informationen zu den **LC_COLLATE** Kategorie finden Sie unter [Setlocale](setlocale-wsetlocale.md) und [Gebietsschemakategorien](../../c-runtime-library/locale-categories.md). Die Versionen dieser Funktionen ohne das **_l** -Suffix verwenden das aktuelle Gebietsschema; die Versionen mit dem **_l** -Suffix sind beinahe identisch, außer dass sie das übergebene Gebietsschema verwenden. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Mit allen diesen Funktionen werden ihre Parameter überprüft. Wenn entweder *string1* oder *Zeichenfolge2* sind **NULL** Zeigern, die Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **_NLSCMPERROR** und **Errno** zu **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicoll**|**_stricoll**|**_mbsicoll**|**_wcsicoll**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_stricoll**, **_stricoll_l**|\<string.h>|
|**_wcsicoll**, **_wcsicoll_l**|\<wchar.h>, \<string.h>|
|**_mbsicoll**, **_mbsicoll_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Locale](../../c-runtime-library/locale.md)<br/>
[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
