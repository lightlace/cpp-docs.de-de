---
title: strncmp, wcsncmp, _mbsncmp, _mbsncmp_l
ms.date: 11/04/2016
apiname:
- strncmp
- _mbsncmp
- wcsncmp
- _mbsncmp_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _ftcsnccmp
- _ftcsncmp
- _tcsncmp
- _tcsnccmp
- strncmp
- _mbsncmp
- wcsncmp
helpviewer_keywords:
- _tcsnccmp function
- ftcsncmp function
- wcsncmp function
- _ftcsncmp function
- _mbsncmp function
- tcsncmp function
- mbsncmp function
- _mbsncmp_l function
- mbsncmp_l function
- strncmp function
- strings [C++], comparing characters of
- string comparison [C++], strncmp function
- _tcsncmp function
- tcsnccmp function
- ftcsnccmp function
- characters [C++], comparing
- _ftcsnccmp function
ms.assetid: 2fdbf4e6-77da-4b59-9086-488f6066b8af
ms.openlocfilehash: 8f022dec6c161814ade5c6be5aaccfcd239a4af4
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210912"
---
# <a name="strncmp-wcsncmp-mbsncmp-mbsncmpl"></a>strncmp, wcsncmp, _mbsncmp, _mbsncmp_l

Vergleicht die angegebene Anzahl von Zeichen zweier Zeichenfolgen.

> [!IMPORTANT]
> **_mbsncmp** und **_mbsncmp_l** kann nicht verwendet werden, in Anwendungen, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int strncmp(
   const char *string1,
   const char *string2,
   size_t count
);
int wcsncmp(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count
);
int _mbsncmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsncmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);int _mbsnbcmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>Parameter

*string1*, *string2*<br/>
Zu vergleichende Zeichenfolgen.

*count*<br/>
Anzahl der zu vergleichenden Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert gibt an, die Beziehung der Teilzeichenfolgen von *string1* und *Zeichenfolge2* wie folgt.

|Rückgabewert|Beschreibung|
|------------------|-----------------|
|< 0|*Zeichenfolge1* Teilzeichenfolge höchstens *Zeichenfolge2* Teilzeichenfolge|
|0|*Zeichenfolge1* identisch *Zeichenfolge2* Teilzeichenfolge|
|> 0|*Zeichenfolge1* größer als *Zeichenfolge2* Teilzeichenfolge|

Bei einem parametervalidierungsfehler **_mbsncmp** und **_mbsncmp_l** zurückgeben **_NLSCMPERROR**, definiert in \<string.h > und \< MBSTRING.h >.

## <a name="remarks"></a>Hinweise

Die **Strncmp** -Funktion führt einen Ordinalvergleich von höchstens der ersten *Anzahl* Zeichen in *string1* und *Zeichenfolge2* und Gibt einen Wert, der die Beziehung zwischen den untergeordneten Zeichenfolgen. **Strncmp** ist eine Groß-/Kleinschreibung Version **_strnicmp**. **Wcsncmp** und **_mbsncmp** werden Groß-/Kleinschreibung Versionen **_wcsnicmp** und **_mbsnicmp**.

**Wcsncmp** und **_mbsncmp** sind Breitzeichen- und multibytezeichenversionen von Versionen von **Strncmp**. Die Argumente des **Wcsncmp** sind Breitzeichen-Zeichenfolgen, die von **_mbsncmp** sind Multibyte Zeichenfolgen. **_mbsncmp** erkennt multibytezeichensequenzen gemäß der Mehrbyte-Codepage und gibt **_NLSCMPERROR** bei einem Fehler.

Darüber hinaus **_mbsncmp** und **_mbsncmp_l** Parameter überprüft. Wenn *string1* oder *Zeichenfolge2* ist ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **_mbsncmp** und **_mbsncmp_l** zurückgeben **_NLSCMPERROR** und **Errno** zu  **EINVAL**. **Strncmp** und **Wcsncmp** überprüfen ihre Parameter nicht. Anderenfalls verhalten sich diese Funktionen identisch.

Das Vergleichsverhalten von **_mbsncmp** und **_mbsncmp_l** wird von der Einstellung beeinflusst die **LC_CTYPE** -kategorieeinstellung des Gebietsschemas. Hierdurch wird die Erkennung von vorangestellten und nachfolgenden Bytes von Multibytezeichen gesteuert. Weitere Informationen finden Sie unter [setlocale](setlocale-wsetlocale.md). Die **_mbsncmp** Funktion verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten. Die **_mbsncmp_l** -Funktion ist identisch, außer dass mithilfe der *Gebietsschema* Parameter stattdessen. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md). Wenn das Gebietsschema ein Einzelbyte-Gebietsschema ist, ist das Verhalten dieser Funktionen mit **Strncmp**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnccmp**|**strncmp**|**_mbsncmp**|**wcsncmp**|
|**_tcsncmp**|**strncmp**|**_mbsnbcmp**|**wcsncmp**|
|**_tccmp**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|**_mbsncmp**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|
|**Nicht zutreffend**|**Nicht zutreffend**|**_mbsncmp_l**|**Nicht zutreffend**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strncmp**|\<string.h>|
|**wcsncmp**|\<string.h> oder \<wchar.h>|
|**_mbsncmp**, **_mbsncmp_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_strncmp.c
#include <string.h>
#include <stdio.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown fox jumps over the lazy dog";

int main( void )
{
   char tmp[20];
   int result;
   printf( "Compare strings:\n      %s\n      %s\n\n",
           string1, string2 );
   printf( "Function:   strncmp (first 10 characters only)\n" );
   result = strncmp( string1, string2 , 10 );
   if( result > 0 )
      strcpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, sizeof(tmp), "less than" );
   else
      strcpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:      String 1 is %s string 2\n\n", tmp );
   printf( "Function:   strnicmp _strnicmp (first 10 characters only)\n" );
   result = _strnicmp( string1, string2, 10 );
   if( result > 0 )
      strcpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, sizeof(tmp), "less than" );
   else
      strcpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:      String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
      The quick brown dog jumps over the lazy fox
      The QUICK brown fox jumps over the lazy dog

Function:   strncmp (first 10 characters only)
Result:      String 1 is greater than string 2

Function:   strnicmp _strnicmp (first 10 characters only)
Result:      String 1 is equal to string 2
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
