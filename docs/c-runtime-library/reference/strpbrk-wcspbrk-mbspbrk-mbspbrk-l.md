---
title: strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
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
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
dev_langs:
- C++
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd62d95e971ac5fd927cce1b7b4eb600ebcf7df6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415877"
---
# <a name="strpbrk-wcspbrk-mbspbrk-mbspbrkl"></a>strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l

Durchsucht Zeichenfolgen nach Zeichen in angegebenen Zeichensätzen.

> [!IMPORTANT]
> **_mbspbrk** und **_mbspbrk_l** kann nicht in Anwendungen, die in der Windows-Runtime ausgeführt verwendet werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
char *strpbrk(
   const char *str,
   const char *strCharSet
); // C only
char *strpbrk(
   char *str,
   const char *strCharSet
); // C++ only
const char *strpbrk(
   const char *str,
   const char *strCharSet
); // C++ only
wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C only
wchar_t *wcspbrk(
   wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
const wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C only
unsigned char *_mbspbrk(
   unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
const unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C only
unsigned char *_mbspbrk_l(
   unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C++ only
const unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char* strCharSet,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*str*<br/>
Auf NULL endende gesuchte Zeichenfolge.

*strCharSet*<br/>
Mit NULL endender Zeichensatz.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf das erste Vorkommen eines beliebigen Zeichens von *StrCharSet* in *str*, oder ein **NULL** Zeiger, wenn zwei Zeichenfolgenargumente keine Zeichen enthalten.

## <a name="remarks"></a>Hinweise

Die **Strpbrk** Funktion gibt einen Zeiger auf das erste Vorkommen eines Zeichens in *str* angehört, die den Satz von Zeichen in *StrCharSet*. Die Suche umfasst nicht das abschließende Nullzeichen.

**Wcspbrk** und **_mbspbrk** sind Breitzeichen- und multibytezeichenversionen von **Strpbrk**. Die Argumente und der Rückgabewert von **Wcspbrk** sind Breitzeichen-Zeichenfolgen, die von **_mbspbrk** sind Multibyte Zeichenfolgen.

**_mbspbrk** überprüft die eigenen Parameter. Wenn *str* oder *StrCharSet* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **_mbspbrk** gibt **NULL** und legt **Errno** auf **EINVAL**. **Strpbrk** und **Wcspbrk** überprüfen ihre Parameter nicht. Diese drei Funktionen verhalten sich andernfalls identisch.

**_mbspbrk** ähnelt **_mbscspn** mit dem Unterschied, dass **_mbspbrk** gibt einen Zeiger anstelle eines Werts vom Typ [Size_t](../../c-runtime-library/standard-types.md).

In C akzeptieren diese Funktionen eine ** const ** Zeiger als erstes Argument. In C++ sind zwei Überladungen verfügbar. Die Überladung, die einen Zeiger auf ** const ** gibt einen Zeiger auf **const **; die Version, die einen Zeiger auf nicht-akzeptiert**const ** gibt einen Zeiger auf nicht-** const **. Das Makro **_CRT_CONST_CORRECT_OVERLOADS** wird definiert, wenn sowohl die **const ** und nicht-** const ** Versionen dieser Funktionen sind verfügbar. Wenn Sie das nicht-** const **-Verhalten für beide C++-Überladungen, definieren Sie das Symbol **_CONST_RETURN**.

Der Ausgabewert wird von der Einstellung der beeinflusst die **LC_CTYPE** Kategorie des Gebietsschemas für Weitere Informationen finden Sie unter [Setlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l** -Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Version mit der **_l** -Suffix ist beinahe identisch, außer dass mithilfe den Locale-Parameter Stattdessen übergeben. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcspbrk**|**strpbrk**|**_mbspbrk**|**wcspbrk**|
|**n/v**|**n/v**|**_mbspbrk_l**|**n/v**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**strpbrk**|\<string.h>|
|**wcspbrk**|\<string.h> oder \<wchar.h>|
|**_mbspbrk**, **_mbspbrk_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_strpbrk.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";
   char *result = NULL;

   // Return pointer to first digit in "string".
   printf( "1: %s\n", string );
   result = strpbrk( string, "0123456789" );
   printf( "2: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "3: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "4: %s\n", result );
}
```

```Output
1: The 3 men and 2 boys ate 5 pigs

2: 3 men and 2 boys ate 5 pigs

3: 2 boys ate 5 pigs

4: 5 pigs
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
