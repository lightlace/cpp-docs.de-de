---
title: _strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr
ms.date: 11/04/2016
apiname:
- _mbsupr_l
- _mbsupr
- _strupr_l
- _wcsupr
- _wcsupr_l
- _strupr
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbsupr
- _ftcsupr
- mbsupr
- _tcsupr
- strupr_l
- _fstrupr
- _strupr
- mbsupr_l
- _wcsupr
helpviewer_keywords:
- tcsupr_l function
- mbsupr function
- strupr function
- uppercase, converting strings to
- wcsupr function
- _wcsupr function
- string conversion [C++], case
- ftcsupr function
- _ftcsupr function
- _wcsupr_l function
- wcsupr_l function
- strings [C++], case
- tcsupr function
- _tcsupr_l function
- _fstrupr function
- _strupr_l function
- _mbsupr_l function
- converting case, CRT functions
- fstrupr function
- mbsupr_l function
- strupr_l function
- _strupr function
- _mbsupr function
- _tcsupr function
- strings [C++], converting case
ms.assetid: caac8f16-c233-41b6-91ce-575ec7061b77
ms.openlocfilehash: c3d155ebfdc40c5dd479cffed0b892dd73f80138
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603644"
---
# <a name="strupr-struprl-mbsupr-mbsuprl-wcsuprl-wcsupr"></a>_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr

Konvertiert eine Zeichenfolge in Großbuchstaben. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l](strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md).

> [!IMPORTANT]
> **_mbsupr** und **_mbsupr_l** kann nicht verwendet werden, in Anwendungen, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
char *_strupr(
   char *str
);
wchar_t *_wcsupr(
   wchar_t *str
);
unsigned char *_mbsupr(
   unsigned char *str
);
char *_strupr_l(
   char *str,
   _locale_t locale
);
wchar_t *_wcsupr_l(
   wchar_t *str,
   _locale_t locale
);
unsigned char *_mbsupr_l(
   unsigned char *str,
   _locale_t locale
);
template <size_t size>
char *_strupr(
   char (&str)[size]
); // C++ only
template <size_t size>
wchar_t *_wcsupr(
   wchar_t (&str)[size]
); // C++ only
template <size_t size>
unsigned char *_mbsupr(
   unsigned char (&str)[size]
); // C++ only
template <size_t size>
char *_strupr_l(
   char (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
wchar_t *_wcsupr_l(
   wchar_t (&str)[size],
   _locale_t locale
); // C++ only
template <size_t size>
unsigned char *_mbsupr_l(
   unsigned char (&str)[size],
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*str*<br/>
Großzuschreibende Zeichenfolge.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger zur geänderten Zeichenfolge zurück. Da die Änderung an der jeweiligen Stelle ausgeführt wurde, gleicht der zurückgegebene Zeiger dem als das Eingabeargument übergebenen Zeiger. Kein Rückgabewert ist zur Fehleranzeige reserviert.

## <a name="remarks"></a>Hinweise

Die **_strupr** -Funktion konvertiert an der Stelle, jedem Kleinbuchstaben in *str* in Großbuchstaben. Die Konvertierung richtet sich nach der **LC_CTYPE** -kategorieeinstellung des Gebietsschemas. Andere Zeichen sind nicht betroffen. Weitere Informationen zu **LC_CTYPE**, finden Sie unter [Setlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l** -Suffix verwenden das aktuelle Gebietsschema; die Versionen mit dem **_l** -Suffix sind beinahe identisch, außer dass sie das übergebene Gebietsschema verwenden. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

**_wcsupr** und **_mbsupr** sind Breitzeichen- und multibytezeichenversionen von Versionen von **_strupr**. Der Wert Argument- und Rückgabetypen der **_wcsupr** sind Breitzeichen-Zeichenfolgen, die von **_mbsupr** sind Multibyte Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.

Wenn *str* ist ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, diese Funktionen zurück, die ursprüngliche Zeichenfolge und legen **Errno** zu **EINVAL**.

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsupr**|**_strupr**|**_mbsupr**|**_wcsupr**|
|**_tcsupr_l**|**_strupr_l**|**_mbsupr_l**|**_wcsupr_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_strupr**, **_strupr_l**|\<string.h>|
|**_wcsupr**, **_wcsupr_l**|\<string.h> oder \<wchar.h>|
|**_mbsupr**, **_mbsupr_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Betrachten Sie das Beispiel für [_strlwr](strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md).

## <a name="see-also"></a>Siehe auch

[Locale](../../c-runtime-library/locale.md)<br/>
[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l](strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)<br/>
