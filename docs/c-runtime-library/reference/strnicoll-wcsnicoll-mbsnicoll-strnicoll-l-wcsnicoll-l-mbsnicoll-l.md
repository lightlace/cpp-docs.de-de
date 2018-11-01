---
title: _strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l
ms.date: 11/04/2016
apiname:
- _mbsnicoll_l
- _mbsnicoll
- _wcsnicoll_l
- _strnicoll
- _strnicoll_l
- _wcsnicoll
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
- wcshicoll_l
- _ftcsncicoll
- strnicoll_l
- _wcsnicoll
- mbsnicoll_l
- _strnicoll
- mbsnicoll
- _ftcsnicoll
- wcsnicoll
- _tcsnicoll
- _mbsnicoll
- strinicoll
- _tcsncicoll
helpviewer_keywords:
- code pages, using for string comparisons
- ftcsncicoll function
- mbsnicoll_l function
- _ftcsnicoll function
- mbsnicoll function
- _tcsnicoll function
- _wcsnicoll_l function
- _mbsnicoll function
- tcsncicoll function
- strnicoll function
- _ftcsncicoll function
- wcsnicoll_l function
- _mbsnicoll_l function
- _tcsncicoll function
- strnicoll_l function
- wcsnicoll function
- _strnicoll_l function
- _wcsnicoll function
- ftcsnicoll function
- strings [C++], comparing by code page
- tcsnicoll function
- _strnicoll function
ms.assetid: abf0c569-725b-428d-9ff2-924f430104b4
ms.openlocfilehash: 6b3562dd077b9aa80b9d188e9b2c43282e797af3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606036"
---
# <a name="strnicoll-wcsnicoll-mbsnicoll-strnicolll-wcsnicolll-mbsnicolll"></a>_strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l

Vergleicht Zeichenfolgen mithilfe gebietsschemaspezifischen Informationen.

> [!IMPORTANT]
> **_mbsnicoll** und **_mbsnicoll_l** kann nicht verwendet werden, in Anwendungen, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _strnicoll(
   const char *string1,
   const char *string2,
   size_t count
);
int _wcsnicoll(
   const wchar_t *string1,
   const wchar_t *string2 ,
   size_t count
);
int _mbsnicoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _strnicoll_l(
   const char *string1,
   const char *string2,
   size_t count,
   _locale_t locale
);
int _wcsnicoll_l(
   const wchar_t *string1,
   const wchar_t *string2 ,
   size_t count,
   _locale_t locale
);
int _mbsnicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*Zeichenfolge1*, *Zeichenfolge2*<br/>
Zu vergleichende mit NULL endende Zeichenfolgen

*count*<br/>
Anzahl der zu vergleichenden Zeichen

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Wert, der die Beziehung der Teilzeichenfolgen von *string1* und *Zeichenfolge2*wie folgt.

|Rückgabewert|Verhältnis von string1 zu string2|
|------------------|----------------------------------------|
|< 0|*Zeichenfolge1* kleiner als *Zeichenfolge2*|
|0|*Zeichenfolge1* identisch mit *Zeichenfolge2*|
|> 0|*Zeichenfolge1* größer als *Zeichenfolge2*|

Jede dieser Funktionen gibt **_NLSCMPERROR**. Verwendung von **_NLSCMPERROR**, entweder Zeichenfolge enthalten. H oder MBSTRING. H. **_wcsnicoll** kann fehlschlagen, wenn *string1* oder *Zeichenfolge2* breitzeichencodes außerhalb der Domäne der Sortierreihenfolge enthält. Wenn ein Fehler auftritt, **_wcsnicoll** kann festgelegt **Errno** zu **EINVAL**. Zu prüfen, ein Fehler bei einem Aufruf von **_wcsnicoll**legen **Errno** auf 0, und klicken Sie dann überprüfen **Errno** nach dem Aufruf **_wcsnicoll**.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen vergleicht Groß-/Kleinschreibung der ersten *Anzahl* Zeichen in *string1* und *Zeichenfolge2* gemäß der Codepage. Diese Funktionen sollten nur verwendet werden, wenn es in der Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Reihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist. Die Versionen dieser Funktionen ohne das **_l** -Suffix verwenden die aktuelle Gebietsschema- und Codepage-Seite. Die Versionen mit dem **_l** -Suffix sind beinahe identisch, außer dass sie das übergebene Gebietsschema verwenden. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Mit allen diesen Funktionen werden ihre Parameter überprüft. Wenn entweder *string1* oder *Zeichenfolge2* ein null-Zeiger ist oder wenn die Anzahl übersteigt **INT_MAX**, Handler für ungültige Parameter aufgerufen, siehe [ Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **_NLSCMPERROR** und **Errno** zu **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncicoll**|**_strnicoll**|**_mbsnbicoll**|**_wcsnicoll**|
|**_tcsnicoll**|**_strnicoll**|[_mbsnbicoll](mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|**_wcsnicoll**|
|**_tcsnicoll_l**|**_strnicoll_l**|**_mbsnbicoll_l**|**_wcsnicoll_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_strnicoll**, **_strnicoll_l**|\<string.h>|
|**_wcsnicoll**, **_wcsnicoll_l**|\<wchar.h> oder \<string.h>|
|**_mbsnicoll**, **_mbsnicoll_l**|\<mbstring.h>|

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
