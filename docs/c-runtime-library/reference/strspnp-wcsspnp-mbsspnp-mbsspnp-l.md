---
title: _strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l
ms.date: 11/04/2016
api_name:
- _mbsspnp
- _wcsspnp
- _mbsspnp_l
- _strspnp
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
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsspnp
- _mbsspnp
- strspnp
- _ftcsspnp
- _mbsspnp_l
- wcsspnp
- mbsspnp_l
- _wcsspnp
- _strspnp
- mbsspnp
helpviewer_keywords:
- _strspnp function
- _wcsspnp function
- _mbsspnp_l function
- strspnp function
- mbsspnp function
- wcsspnp function
- _mbsspnp function
- mbsspnp_l function
- _tcsspnp function
- tcsspnp function
ms.assetid: 1ce18100-2edd-4c3b-af8b-53f204d80233
ms.openlocfilehash: af80f4970e5aad4355b0287c901f130809cc4f79
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946681"
---
# <a name="_strspnp-_wcsspnp-_mbsspnp-_mbsspnp_l"></a>_strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l

Gibt einen Zeiger auf das erste Zeichen in einer bestimmten Zeichenfolge zurück, das nicht in einer anderen angegebenen Zeichenfolge ist.

> [!IMPORTANT]
> **_mbsspnp** und **_mbsspnp_l** können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
char *_strspnp(
   const char *str,
   const char *charset
);
wchar_t *_wcsspnp(
   const unsigned wchar_t *str,
   const unsigned wchar_t *charset
);
unsigned char *_mbsspnp(
   const unsigned char *str,
   const unsigned char *charset
);
unsigned char *_mbsspnp_l(
   const unsigned char *str,
   const unsigned char *charset,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Zu suchende mit NULL endende Zeichenfolge.

*charset*<br/>
Mit NULL endender Zeichensatz.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_strspnp**, **_wcsspnp**und **_mbsspnp** geben einen Zeiger auf das erste Zeichen in *Str* zurück, das nicht zum Zeichensatz in *CharSet*gehört. Jede dieser Funktionen gibt **null** zurück, wenn *Str* vollständig aus Zeichen aus *CharSet*besteht. Für diese Routinen ist kein Rückgabewert zur Anzeige eines Fehlers reserviert.

## <a name="remarks"></a>Hinweise

Die **_mbsspnp** -Funktion gibt einen Zeiger auf das Multibytezeichen zurück, das das erste Zeichen in *Str* ist, das nicht zum Zeichensatz in *CharSet*gehört. **_mbsspnp** erkennt multibytezeichensequenzen gemäß der derzeit verwendeten [Multibytezeichen-Codepage](../../c-runtime-library/code-pages.md) . Die Suche umfasst keine abschließenden Nullzeichen.

Wenn entweder *Str* oder *CharSet* ein NULL-Zeiger ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion **null** zurück und legt **errno** auf **EINVAL**fest.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsspnp**|**_strspnp**|**_mbsspnp**|**_wcsspnp**|

**_strspnp** und **_wcsspnp** sind Einzel Byte Zeichen-und breit Zeichen Versionen von **_mbsspnp**. **_strspnp** und **_wcsspnp** Verhalten sich identisch mit **_mbsspnp** ; andernfalls; Sie werden nur für diese Zuordnung bereitgestellt und sollten nicht aus anderen Gründen verwendet werden. Weitere Informationen finden Sie unter [Verwenden von Zuordnungen für generischen Text](../../c-runtime-library/using-generic-text-mappings.md) und [Textzuordnungen für generischen Text](../../c-runtime-library/generic-text-mappings.md).

**_mbsspnp_l** ist beinahe identisch, verwendet jedoch stattdessen den übergebenen Gebiets Schema Parameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbsspnp**|\<mbstring.h>|
|**_strspnp**|\<tchar.h>|
|**_wcsspnp**|\<tchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_mbsspnp.c
#include <mbstring.h>
#include <stdio.h>

int main( void ) {
   const unsigned char string1[] = "cabbage";
   const unsigned char string2[] = "c";
   unsigned char *ptr = 0;
   ptr = _mbsspnp( string1, string2 );
   printf( "%s\n", ptr);
}
```

### <a name="output"></a>Ausgabe

```Output
abbage
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
