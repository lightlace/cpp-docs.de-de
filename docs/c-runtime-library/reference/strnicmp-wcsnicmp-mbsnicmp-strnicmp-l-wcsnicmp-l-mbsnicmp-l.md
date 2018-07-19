---
title: _strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wcsnicmp
- _strnicmp_l
- _wcsnicmp_l
- _strnicmp
- _mbsnicmp
- _mbsnicmp_l
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wcsnicmp_l
- _strnicmp
- _ftcsnicmp
- mbsnicmp_l
- _ftcsncicmp
- mbsnicmp
- _tcsncicmp
- _mbsnicmp
- _tcsnicmp
- strnicmp_l
- _wcsnicmp
- _wcsnicmp_l
- CORECRT_WSTRING/_wcsnicmp
- CORECRT_WSTRING/_wcsnicmp_l
- string/_strnicmp
- string/_strnicmp_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnicmp function
- _tcsncicmp function
- _mbsnicmp_l function
- mbsnicmp_l function
- wcsnicmp_l function
- wcsnicmp function
- string comparison [C++], lowercase
- ftcsnicmp function
- strnicmp_l function
- strncmp function
- _strnicmp function
- strings [C++], comparing characters of
- _wcsnicmp_l function
- tcsncicmp function
- string comparison [C++], strncmp function
- _mbsnicmp function
- ftcsncicmp function
- _tcsnicmp function
- _ftcsncicmp function
- _strnicmp_l function
- _ftcsnicmp function
- characters [C++], comparing
- mbsnicmp function
- _wcsnicmp function
ms.assetid: df6e5037-4039-4c85-a0a6-21d4ef513966
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba97d3bcd356a044245e7613470bead1cc42eb25
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417128"
---
# <a name="strnicmp-wcsnicmp-mbsnicmp-strnicmpl-wcsnicmpl-mbsnicmpl"></a>_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l
Vergleicht die angegebene Anzahl von Zeichen zweier Zeichenfolgen ohne Berücksichtigung von Groß-/Kleinbuchstaben.

> [!IMPORTANT]
> **_mbsnicmp** und **_mbsnicmp_l** kann nicht in Anwendungen, die in der Windows-Runtime ausgeführt verwendet werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _strnicmp(
   const char *string1,
   const char *string2,
   size_t count
);
int _wcsnicmp(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count
);
int _mbsnicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _strnicmp_l(
   const char *string1,
   const char *string2,
   size_t count,
   _locale_t locale
);
int _wcsnicmp_l(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count,
   _locale_t locale
);
int _mbsnicmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*String1*, *Zeichenfolge2*<br/>
Zu vergleichende mit NULL endende Zeichenfolgen.

*count*<br/>
Anzahl der zu vergleichenden Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt die Beziehung zwischen den untergeordneten Zeichenfolgen wie folgt an.

|Rückgabewert|Beschreibung|
|------------------|-----------------|
|< 0|*String1* Teilzeichenfolge ist kleiner als *Zeichenfolge2* Teilzeichenfolge.|
|0|*String1* Teilzeichenfolge ist identisch mit *Zeichenfolge2* Teilzeichenfolge.|
|> 0|*String1* Teilzeichenfolge ist größer als *Zeichenfolge2* Teilzeichenfolge.|

Bei einem parametervalidierungsfehler geben diese Funktionen zurück **_NLSCMPERROR**, definiert \<string.h > und \<mbstring.h >.

## <a name="remarks"></a>Hinweise

Die **_strnicmp** -Funktion vergleicht Ordinal höchstens die ersten *Anzahl* Zeichen des *string1* und *Zeichenfolge2*. Der Vergleich erfolgt ohne Berücksichtigung der Groß-/Kleinschreibung, indem jedes Zeichen in Kleinbuchstaben konvertiert wird. **_strnicmp** ist eine Groß-/Kleinschreibung Version von **Strncmp**. Der Vergleich endet, wenn ein abschließendes Nullzeichen, in jeder Zeichenfolge vor dem erreicht wird *Anzahl* Zeichen verglichen wurden. Wenn die Zeichenfolgen gleich sind. wenn ein abschließendes Nullzeichen erreicht ist in jeder Zeichenfolge vor dem *Anzahl* Zeichen verglichen wurden, ist die kürzere Zeichenfolge kleiner.

Die Zeichen von 91 bis 96 in der ASCII-Tabelle ('[', '\\', ']', '^', '_' und '\`') werden als kleiner als jedes beliebige alphabetische Zeichen ausgewertet. Diese Reihenfolge ist identisch mit der **Stricmp**.

**_wcsnicmp** und **_mbsnicmp** sind Breitzeichen- und multibytezeichenversionen von **_strnicmp**. Die Argumente der **_wcsnicmp** sind Breitzeichen-Zeichenfolgen, die von **_mbsnicmp** sind Multibyte Zeichenfolgen. **_mbsnicmp** erkennt Multibyte-Zeichenfolgen entsprechend der aktuellen multibyte-Codepage und gibt **_NLSCMPERROR** bei einem Fehler. Weitere Informationen finden Sie unter [Codepages](../../c-runtime-library/code-pages.md). Diese drei Funktionen verhalten sich andernfalls identisch. Diese Funktionen werden von der gebietsschemaeinstellung beeinflusst – die Versionen nicht mit der **_l** -Suffix verwenden das aktuelle Gebietsschema für ihr vom Gebietsschema abhängige Verhalten; die Versionen, auf denen die **_l** Suffix Verwenden Sie stattdessen die *Gebietsschema* übergeben wird. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Mit allen diesen Funktionen werden ihre Parameter überprüft. Wenn entweder *string1* oder *Zeichenfolge2* ist ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **_NLSCMPERROR** und **Errno** auf **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncicmp**|**_strnicmp**|**_mbsnicmp**|**_wcsnicmp**|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsncicmp_l**|**_strnicmp_l**|**_mbsnicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_strnicmp**, **_strnicmp_l**|<string.h>|
|**_wcsnicmp**, **_wcsnicmp_l**|<string.h> oder <wchar.h>|
|**_mbsnicmp**, **_mbsnicmp_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
