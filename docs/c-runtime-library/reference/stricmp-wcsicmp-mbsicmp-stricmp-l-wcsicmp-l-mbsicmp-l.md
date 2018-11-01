---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
ms.date: 11/04/2016
apiname:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
ms.openlocfilehash: d27b2128d79d7ff3ab0150e182d494fed52d46ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559075"
---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l

Führt einen Vergleich von Zeichenfolgen ohne Beachtung der Groß-/Kleinschreibung durch.

> [!IMPORTANT]
> **_mbsicmp** und **_mbsicmp_l** kann nicht verwendet werden, in Anwendungen, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _stricmp(
   const char *string1,
   const char *string2
);
int _wcsicmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbsicmp(
   const unsigned char *string1,
   const unsigned char *string2
);
int _stricmp_l(
   const char *string1,
   const char *string2,
   _locale_t locale
);
int _wcsicmp_l(
   const wchar_t *string1,
   const wchar_t *string2,
   _locale_t locale
);
int _mbsicmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*Zeichenfolge1*, *Zeichenfolge2*<br/>
Zu vergleichende mit NULL endende Zeichenfolgen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert gibt an, die Beziehung zwischen *string1* zu *Zeichenfolge2* wie folgt.

|Rückgabewert|Beschreibung|
|------------------|-----------------|
|< 0|*Zeichenfolge1* kleiner als *Zeichenfolge2*|
|0|*Zeichenfolge1* identisch mit *Zeichenfolge2*|
|> 0|*Zeichenfolge1* größer als *Zeichenfolge2*|

Bei einem Fehler **_mbsicmp** gibt **_NLSCMPERROR**, definiert in \<string.h > und \<mbstring.h >.

## <a name="remarks"></a>Hinweise

Die **_stricmp** -Funktion vergleicht der Reihe *string1* und *Zeichenfolge2* nach der Konvertierung der jedes Zeichen in Kleinbuchstaben, und gibt eines Wert, der ihre Beziehung angibt. **_stricmp** unterscheidet sich von **_stricoll** darin, dass die **_stricmp** hat nur Auswirkungen auf Vergleich von **LC_CTYPE**, der bestimmt, welche Zeichen oberen sind und Kleinbuchstaben. Die **_stricoll** Funktion vergleicht Zeichenfolgen gemäß der **LC_CTYPE** und **LC_COLLATE** Kategorien des Gebietsschemas, die die Groß-/Kleinschreibung und Sortierung umfasst die Reihenfolge. Weitere Informationen zu den **LC_COLLATE** Kategorie finden Sie unter [Setlocale](setlocale-wsetlocale.md) und [Gebietsschemakategorien](../../c-runtime-library/locale-categories.md). Die Versionen dieser Funktionen ohne das **_l** -Suffix verwenden das aktuelle Gebietsschema für gebietsschemaabhängige Verhalten. Die Versionen mit dem Suffix sind identisch, verwenden allerdings das übergebene Gebietsschema. Wenn das Gebietsschema nicht festgelegt wurde, wird das C-Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> **_stricmp** entspricht **_strcmpi**. Sie können austauschbar verwendet werden, aber **_stricmp** ist der bevorzugte Standard.

Die **_strcmpi** -Funktion ist gleichbedeutend mit **_stricmp** und wird nur zur Abwärtskompatibilität bereitgestellt.

Da **_stricmp** kleinbuchstabenvergleiche ausführt, kann es zu unerwartetem Verhalten führen.

Um zu veranschaulichen, wann kleinschreibungskonvertierung durch **_stricmp** wirkt sich auf das Ergebnis eines Vergleichs wird davon ausgegangen, dass Sie die beiden Zeichenfolgen JOHNSTON und JOHN_HENRY verfügen. Die Zeichenfolge JOHN_HENRY wird als kleiner als JOHNSTON angesehen, da das Zeichen „_“ einen niedrigeren ASCII-Wert hat als der Kleinbuchstabe „s“. Jedes Zeichen mit einem ASCII-Wert zwischen 91 und 96 wird als kleiner als jeder Buchstabe angesehen.

Wenn die [Strcmp](strcmp-wcscmp-mbscmp.md) Funktion dient anstelle von **_stricmp**, john_henry größer als JOHNSTON.

**_wcsicmp** und **_mbsicmp** sind Breitzeichen- und multibytezeichenversionen von Versionen von **_stricmp**. Die Argumente und der Rückgabewert von **_wcsicmp** sind Breitzeichen-Zeichenfolgen, die von **_mbsicmp** sind Multibyte Zeichenfolgen. **_mbsicmp** erkennt multibytezeichensequenzen gemäß der aktuellen multibyte-Codepage und gibt **_NLSCMPERROR** bei einem Fehler. Weitere Informationen finden Sie unter [Codepages](../../c-runtime-library/code-pages.md). Diese drei Funktionen verhalten sich andernfalls identisch.

**_wcsicmp** und **Wcscmp** Verhalten sich identisch, außer dass **Wcscmp** Argumente in Kleinbuchstaben, bevor diese verglichen werden nicht konvertiert. **_mbsicmp** und **_mbscmp** Verhalten sich identisch, außer dass **_mbscmp** Argumente in Kleinbuchstaben, bevor diese verglichen werden nicht konvertiert.

Sie müssen Aufrufen [Setlocale](setlocale-wsetlocale.md) für **_wcsicmp** mit Latin 1-Zeichen funktionieren. Das C-Gebietsschema ist standardmäßig aktiviert, deshalb ist z. B. "ä" nicht identisch mit "Ä". Rufen Sie **Setlocale** mit einem anderen Gebietsschema als das Gebietsschema "C" vor dem Aufruf von **_wcsicmp**. Im folgende Beispiel wird veranschaulicht, wie **_wcsicmp** ist vom Gebietsschema abhängt:

```C
// crt_stricmp_locale.c
#include <string.h>
#include <stdio.h>
#include <locale.h>

int main() {
   setlocale(LC_ALL,"C");   // in effect by default
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails
   setlocale(LC_ALL,"");
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds
}
```

Eine Alternative besteht darin, rufen Sie [_create_locale _wcreate_locale](create-locale-wcreate-locale.md) und übergeben Sie das zurückgegebene Gebietsschemaobjekt als Parameter an **_wcsicmp_l**.

Mit allen diesen Funktionen werden ihre Parameter überprüft. Wenn entweder *string1* oder *Zeichenfolge2* null-Zeiger, der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **_NLSCMPERROR** und **Errno** zu **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsicmp**|**_stricmp**|**_mbsicmp**|**_wcsicmp**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_stricmp**, **_stricmp_l**|\<string.h>|
|**_wcsicmp**, **_wcsicmp_l**|\<string.h> oder \<wchar.h>|
|**_mbsicmp**, **_mbsicmp_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_stricmp.c

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
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof(tmp), "less than" );
   else
      strcpy_s( tmp, _countof(tmp), "equal to" );
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
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
