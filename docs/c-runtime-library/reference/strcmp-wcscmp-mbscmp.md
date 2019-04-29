---
title: strcmp, wcscmp, _mbscmp, _mbscmp_l
ms.date: 01/22/2019
apiname:
- wcscmp
- _mbscmp
- _mbscmp_l
- strcmp
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
- _mbscmp
- _mbscmp_l
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- _mbscmp_l function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
ms.openlocfilehash: dae5e04809ac7312097cb418ab5ffd561fdbd1d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354222"
---
# <a name="strcmp-wcscmp-mbscmp-mbscmpl"></a>strcmp, wcscmp, _mbscmp, _mbscmp_l

Vergleichen von Zeichenfolgen

> [!IMPORTANT]
> **_mbscmp** und **_mbscmp_l** kann nicht verwendet werden, in Anwendungen, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int strcmp(
   const char *string1,
   const char *string2
);
int wcscmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _mbscmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*string1*, *string2*<br/>
Zu vergleichende mit NULL endende Zeichenfolgen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert für jede dieser Funktionen gibt die ordinalbeziehung von *string1* zu *Zeichenfolge2*.

|Wert|Verhältnis von string1 zu string2|
|-----------|----------------------------------------|
|< 0|*Zeichenfolge1* ist kleiner als *Zeichenfolge2*|
|0|*Zeichenfolge1* ist identisch mit *Zeichenfolge2*|
|> 0|*Zeichenfolge1* ist größer als *Zeichenfolge2*|

Bei einem parametervalidierungsfehler **_mbscmp** und **_mbscmp_l** zurückgeben **_NLSCMPERROR**, definiert in \<string.h > und \< MBSTRING.h >.

## <a name="remarks"></a>Hinweise

Die **Strcmp** -Funktion führt einen Ordinalvergleich von *string1* und *Zeichenfolge2* und gibt einen Wert, der ihre Beziehung angibt. **Wcscmp** und **_mbscmp** sind Breitzeichen- und multibytezeichenversionen von Versionen von **Strcmp**. **_mbscmp** erkennt multibytezeichensequenzen gemäß der aktuellen multibyte-Codepage und gibt **_NLSCMPERROR** bei einem Fehler. **_mbscmp_l** weist das gleiche Verhalten, aber den Locale-Parameter, die übergeben wird anstelle des aktuellen Gebietsschemas verwendet. Weitere Informationen finden Sie unter [Codepages](../../c-runtime-library/code-pages.md). Auch wenn *string1* oder *Zeichenfolge2* ist ein null-Zeiger **_mbscmp** wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **_mbscmp** und **_mbscmp_l** zurückgeben **_NLSCMPERROR** und **Errno** zu **EINVAL** . **Strcmp** und **Wcscmp** überprüfen ihre Parameter nicht. Anderenfalls verhalten sich diese Funktionen identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**strcmp**|**_mbscmp**|**wcscmp**|

Die **Strcmp** Funktionen unterscheiden sich von der **Strcoll** -Funktionen dahingehend, dass **Strcmp** Vergleiche Ordinalvergleiche darstellen und werden nicht vom Gebietsschema beeinflusst. **Strcoll** vergleicht Zeichenfolgen lexikografisch mithilfe der **LC_COLLATE** -Kategorie des aktuellen Gebietsschemas. Weitere Informationen zu den **LC_COLLATE** Kategorie finden Sie unter [Setlocale, _wsetlocale](setlocale-wsetlocale.md).

Im Gebietsschema "C" ist die Reihenfolge der Zeichen im Zeichensatz (ASCII-Zeichensatz) die gleiche wie die lexikografische Zeichenreihenfolge. In anderen Gebietsschemata kann die Reihenfolge der Zeichen im Zeichensatz jedoch von der lexikografischen Reihenfolge abweichen. In bestimmten europäischen Gebietsschemas steht im Zeichensatz das Zeichen "a" (Wert 0x61) vor dem Zeichen "ä" (Wert 0xE4), das Zeichen "ä" steht jedoch lexikografisch gesehen jedoch vor dem Zeichen "a".

In Gebietsschemas, die für die der Zeichensatz und die lexikografische Zeichenreihenfolge unterschiedlich sind, können Sie **Strcoll** anstelle von **Strcmp** für den lexikografischen Vergleich von Zeichenfolgen. Alternativ können Sie **Strxfrm** auf die ursprünglichen Zeichenfolgen und anschließend auf **Strcmp** für die resultierenden Zeichenfolgen.

Die **Strcmp** Funktionen werden Groß-/Kleinschreibung beachtet. **\_Stricmp**,  **\_Wcsicmp**, und  **\_Mbsicmp** Zeichenfolgen vergleichen, indem Sie sie in Kleinbuchstaben konvertieren. Zwei Zeichenfolgen mit Zeichen, die sich zwischen "Z" befinden und "a" in der ASCII-Tabelle ("[','\\", "]', ' ^', '_', und"\`') unterschiedlich, abhängig von der Großschreibung vergleichen. Z. B. die beiden Zeichenfolgen "ABCDE" und "ABCD ^" eine Richtung verglichen, wenn Kleinschreibung vorliegt ("Abcde" > "Abcd ^") und die andere Möglichkeit ("ABCDE" < "ABCD ^"), wenn Großschreibung vorliegt.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strcmp**|\<string.h>|
|**wcscmp**|\<string.h> oder \<wchar.h>|
|**_mbscmp**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_strcmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof (tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
