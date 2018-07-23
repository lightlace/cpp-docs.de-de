---
title: strrchr, wcsrchr, _mbsrchr, _mbsrchr_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strrchr
- wcsrchr
- _mbsrchr
- _mbsrchr_l
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
apitype: DLLExport
f1_keywords:
- _tcsrchr
- _ftcsrchr
- strrchr
- wcsrchr
- _mbsrchr
dev_langs:
- C++
helpviewer_keywords:
- _mbsrchr function
- tcsrchr function
- mbsrchr_l function
- characters [C++], scanning for
- ftcsrchr function
- _tcsrchr function
- strings [C++], scanning
- mbsrchr function
- strrchr function
- scanning strings
- wcsrchr function
- _ftcsrchr function
- _mbsrchr_l function
ms.assetid: 75cf2664-758e-49bb-bf6b-8a139cd474d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03b0ce2c9bd205f9065c783a4ff4d7e50d0ff803
ms.sourcegitcommit: 04d327940787df1297b72d534f388a035d472af0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2018
ms.locfileid: "39181158"
---
# <a name="strrchr-wcsrchr-mbsrchr-mbsrchrl"></a>strrchr, wcsrchr, _mbsrchr, _mbsrchr_l

Durchsucht eine Zeichenfolge nach dem letzten Vorkommen eines Zeichens.

> [!IMPORTANT]
> `_mbsrchr` und `_mbsrchr_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
char *strrchr(
   const char *str,
   int c
); // C only
char *strrchr(
   char *str,
   int c
); // C++ only
const char *strrchr(
   const char *str,
   int c
); // C++ only
wchar_t *wcsrchr(
   const wchar_t *str,
   wchar_t c
); // C only
wchar_t *wcsrchr(
   wchar_t *str,
   wchar_t c
); // C++ only
const wchar_t *wcsrchr(
   const wchar_t *str,
   wchar_t c
); // C++ only
unsigned char *_mbsrchr(
   const unsigned char *str,
   unsigned int c
); // C only
unsigned char *_mbsrchr(
   unsigned char *str,
   unsigned int c
); // C++ only
const unsigned char *_mbsrchr(
   const unsigned char *str,
   unsigned int c
); // C++ only
unsigned char *_mbsrchr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C only
unsigned char *_mbsrchr_l(
   unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
const unsigned char *_mbsrchr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*str*<br/>
Zu suchende mit NULL endende Zeichenfolge.

*c*<br/>
Zu suchende Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf das letzte Vorkommen der *c* in *str*, oder NULL, wenn *c* wurde nicht gefunden.

## <a name="remarks"></a>Hinweise

Die `strrchr` -Funktion sucht nach dem letzten Eintreten des *c* (konvertiert **Char**) in *str*. Die Suche enthält das abschließende NULL-Zeichen.

`wcsrchr` und `_mbsrchr` sind Breitzeichen- und Multibytezeichenversionen von `strrchr`. Die Argumente und der Rückgabewert von `wcsrchr` sind Breitzeichen-Zeichenfolgen; die von `_mbsrchr` sind Mehrbyte-Zeichenfolgen.

In C akzeptieren diese Funktionen eine **const** Zeiger für das erste Argument. In C++ sind zwei Überladungen verfügbar. Die Überladung, die einen Zeiger auf **const** gibt einen Zeiger auf **const**; die Version, die einen Zeiger auf nicht-akzeptiert**const** gibt einen Zeiger auf nicht-**const** . Das Makro _CRT_CONST_CORRECT_OVERLOADS definiert ist, wenn sowohl die **const** und nicht-**const** Versionen dieser Funktionen sind verfügbar. Wenn Sie nicht benötigen**const** Verhalten für beide C++-Überladungen, definieren Sie das Symbol _CONST_RETURN.

`_mbsrchr` überprüft die eigenen Parameter. Wenn *str* NULL ist, den Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, `errno` nastaven NA hodnotu EINVAL und `_mbsrchr` gibt 0 zurück. `strrchr` und `wcsrchr` überprüfen ihre Parameter nicht. Diese drei Funktionen verhalten sich andernfalls identisch.

Der Ausgabewert ist von der Einstellung von den LC_CTYPE--kategorieeinstellung des Gebietsschemas betroffen; Weitere Informationen finden Sie unter [Setlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcsrchr`|`strrchr`|`_mbsrchr`|`wcsrchr`|
|**n/v**|**n/v**|`_mbsrchr_l`|**n/v**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`strrchr`|\<string.h>|
|`wcsrchr`|\<string.h> oder \<wchar.h>|
|`_mbsrchr`, `_mbsrchr_l`|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von `strrchr` finden Sie unter [strchr](strchr-wcschr-mbschr-mbschr-l.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
