---
title: strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsncpy_s_l
- wcsncpy_s
- _strncpy_s_l
- strncpy_s
- _mbsncpy_s
- _wcsncpy_s_l
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
- _tcsncpy_s
- _wcsncpy_s_l
- strncpy_s
- _strncpy_s_l
- wcsncpy_s
- _tcsncpy_s_l
dev_langs:
- C++
helpviewer_keywords:
- _wcsncpy_s_l function
- _mbsnbcpy_s function
- _tcsncpy_s_l function
- mbsncpy_s function
- strncpy_s_l function
- _strncpy_s_l function
- strncpy_s function
- mbsncpy_s_l function
- wcsncpy_s function
- copying strings
- strings [C++], copying
- _mbsnbcpy_s_l function
- _tcsncpy_s function
- wcsncpy_s_l function
ms.assetid: a971c800-94d1-4d88-92f3-a2fe236a4546
caps.latest.revision: 47
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b78557d7edf1b85922dceff4e672419fae01af6a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="strncpys-strncpysl-wcsncpys-wcsncpysl-mbsncpys-mbsncpysl"></a>strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l

Kopiert Zeichen aus einer Zeichenfolge in eine andere.  Diese Versionen von [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

> [!IMPORTANT]
> **_mbsncpy_s** und **_mbsncpy_s_l** kann nicht in Anwendungen, die in der Windows-Runtime ausgeführt verwendet werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
errno_t strncpy_s(
   char *strDest,
   size_t numberOfElements,
   const char *strSource,
   size_t count
);
errno_t _strncpy_s_l(
   char *strDest,
   size_t numberOfElements,
   const char *strSource,
   size_t count,
   _locale_t locale
);
errno_t wcsncpy_s(
   wchar_t *strDest,
   size_t numberOfElements,
   const wchar_t *strSource,
   size_t count
);
errno_t _wcsncpy_s_l(
   wchar_t *strDest,
   size_t numberOfElements,
   const wchar_t *strSource,
   size_t count,
   _locale_t locale
);
errno_t _mbsncpy_s(
   unsigned char *strDest,
   size_t numberOfElements,
   const unsigned char *strSource,
   size_t count
);
errno_t _mbsncpy_s_l(
   unsigned char *strDest,
   size_t numberOfElements,
   const unsigned char *strSource,
   size_t count,
   locale_t locale
);
template <size_t size>
errno_t strncpy_s(
   char (&strDest)[size],
   const char *strSource,
   size_t count
); // C++ only
template <size_t size>
errno_t _strncpy_s_l(
   char (&strDest)[size],
   const char *strSource,
   size_t count,
   _locale_t locale
); // C++ only
template <size_t size>
errno_t wcsncpy_s(
   wchar_t (&strDest)[size],
   const wchar_t *strSource,
   size_t count
); // C++ only
template <size_t size>
errno_t _wcsncpy_s_l(
   wchar_t (&strDest)[size],
   const wchar_t *strSource,
   size_t count,
   _locale_t locale
); // C++ only
template <size_t size>
errno_t _mbsncpy_s(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsncpy_s_l(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*strDest*<br/>
Zielzeichenfolge.

*numberOfElements*<br/>
Die Größe der Zielzeichenfolge in Zeichen.

*strSource*<br/>
Quellzeichenfolge.

*count*<br/>
Anzahl der zu kopierenden Zeichen oder [_TRUNCATE](../../c-runtime-library/truncate.md).

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

NULL Wenn erfolgreich, **STRUNCATE** bei abgeschnittenen Daten, andernfalls einen Fehlercode.

### <a name="error-conditions"></a>Fehlerbedingungen

|*strDest*|*numberOfElements*|*strSource*|Rückgabewert|Inhalt der *StrDest*|
|---------------|------------------------|-----------------|------------------|---------------------------|
|**NULL**|alle|alle|**EINVAL**|nicht geändert|
|alle|alle|**NULL**|**EINVAL**|*StrDest*[0] auf 0 festgelegt|
|alle|0|alle|**EINVAL**|nicht geändert|
|nicht **NULL**|zu klein|alle|**ERANGE**|*StrDest*[0] auf 0 festgelegt|

## <a name="remarks"></a>Hinweise

Diese Funktionen versuchen, kopieren Sie die erste *D* Zeichen des *StrSource* auf *StrDest*, wobei *D* weniger als *Anzahl*  und die Länge des *StrSource*. Wenn diese *D* Zeichen passt in *StrDest* (erhält, dessen Größe als *NumberOfElements*) und noch Platz für ein null-Abschlusszeichen, und klicken Sie dann diese Zeichen kopiert werden und ein abschließendes Nullzeichen angefügt ist. andernfalls *StrDest*[0] festgelegt ist, das Null-Zeichen und den ungültigen Parameter Handler aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md).

Zu der oberen Aufführung gibt es eine Ausnahme. Wenn *Anzahl* ist **_TRUNCATE**, wird so viel von *StrSource* als wird entsprechend in *StrDest* kopiert, wobei noch Platz für bleibt die Beenden von Null das immer angefügt wird.

Ein auf ein Objekt angewendeter

```C
char dst[5];
strncpy_s(dst, 5, "a long string", 5);
```

bedeutet, die wir Navigationssystem **Strncpy_s** So kopieren Sie fünf Zeichen in einen Puffer fünf Bytes langen; somit gäbe es keinen Platz für das Nullabschlusszeichen daher **Strncpy_s** weist der Zeichenfolge und ruft den ungültigen Handler für den Parameter.

Wenn ein abschneideverhalten erforderlich ist, verwenden Sie **_TRUNCATE** oder (*Größe* - 1):

```C
strncpy_s(dst, 5, "a long string", _TRUNCATE);
strncpy_s(dst, 5, "a long string", 4);
```

Beachten Sie, dass im Gegensatz zu **Strncpy**, wenn *Anzahl* ist größer als die Länge des *StrSource*, die Zielzeichenfolge mit Nullzeichen bis zur Länge nichtaufgefülltwird*Anzahl*.

Das Verhalten des **Strncpy_s** ist undefiniert, wenn die Quell- und Zielzeichenfolgen überlappen.

Wenn *StrDest* oder *StrSource* ist **NULL**, oder *NumberOfElements* gleich 0 ist, wird der Handler für ungültige Parameter aufgerufen. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion **EINVAL** und legt **Errno** auf **EINVAL**.

**Wcsncpy_s** und **_mbsncpy_s** sind Breitzeichen- und multibytezeichenversionen von **Strncpy_s**. Die Argumente und der Rückgabewert von **Wcsncpy_s** und **Mbsncpy_s** unterscheiden sich entsprechend. Diese sechs Funktionen verhalten sich andernfalls identisch.

Der Ausgabewert wird von der Einstellung der beeinflusst die **LC_CTYPE** -kategorieneinstellung des Gebietsschemas; Siehe [Setlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncpy_s**|**strncpy_s**|**_mbsnbcpy_s**|**wcsncpy_s**|
|**_tcsncpy_s_l**|**_strncpy_s_l**|**_mbsnbcpy_s_l**|**_wcsncpy_s_l**|

> [!NOTE]
> **_strncpy_s_l**, **_wcsncpy_s_l** und **_mbsncpy_s_l** haben keine gebietsschemaabhängigkeit und sind nur aus Gründen **_tcsncpy_s_l** und sollten nicht verwendet werden direkt aufgerufen.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Strncpy_s**, **_strncpy_s_l**|\<string.h>|
|**Wcsncpy_s**, **_wcsncpy_s_l**|\<string.h> oder \<wchar.h>|
|**_mbsncpy_s**, **_mbsncpy_s_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```cpp
// crt_strncpy_s_1.cpp
// compile with: /MTd

// these #defines enable secure template overloads
// (see last part of Examples() below)
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <crtdbg.h>  // For _CrtSetReportMode
#include <errno.h>

// This example uses a 10-byte destination buffer.

errno_t strncpy_s_tester( const char * src,
                          int count )
{
   char dest[10];

   printf( "\n" );

   if ( count == _TRUNCATE )
      printf( "Copying '%s' to %d-byte buffer dest with truncation semantics\n",
               src, _countof(dest) );
   else
      printf( "Copying %d chars of '%s' to %d-byte buffer dest\n",
              count, src, _countof(dest) );

   errno_t err = strncpy_s( dest, _countof(dest), src, count );

   printf( "    new contents of dest: '%s'\n", dest );

   return err;
}

void Examples()
{
   strncpy_s_tester( "howdy", 4 );
   strncpy_s_tester( "howdy", 5 );
   strncpy_s_tester( "howdy", 6 );

   printf( "\nDestination buffer too small:\n" );
   strncpy_s_tester( "Hi there!!", 10 );

   printf( "\nTruncation examples:\n" );

   errno_t err = strncpy_s_tester( "How do you do?", _TRUNCATE );
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"
                                                       : "did not" );

   err = strncpy_s_tester( "Howdy.", _TRUNCATE );
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"
                                                       : "did not" );

   printf( "\nSecure template overload example:\n" );

   char dest[10];
   strncpy( dest, "very very very long", 15 );
   // With secure template overloads enabled (see #defines at
   // top of file), the preceding line is replaced by
   //    strncpy_s( dest, _countof(dest), "very very very long", 15 );
   // Instead of causing a buffer overrun, strncpy_s invokes
   // the invalid parameter handler.
   // If secure template overloads were disabled, strncpy would
   // copy 15 characters and overrun the dest buffer.
   printf( "    new contents of dest: '%s'\n", dest );
}

void myInvalidParameterHandler(
   const wchar_t* expression,
   const wchar_t* function,
   const wchar_t* file,
   unsigned int line,
   uintptr_t pReserved)
{
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);
}

int main( void )
{
   _invalid_parameter_handler oldHandler, newHandler;

   newHandler = myInvalidParameterHandler;
   oldHandler = _set_invalid_parameter_handler(newHandler);
   // Disable the message box for assertions.
   _CrtSetReportMode(_CRT_ASSERT, 0);

   Examples();
}
```

```Output
Copying 4 chars of 'howdy' to 10-byte buffer dest
    new contents of dest: 'howd'

Copying 5 chars of 'howdy' to 10-byte buffer dest
    new contents of dest: 'howdy'

Copying 6 chars of 'howdy' to 10-byte buffer dest
    new contents of dest: 'howdy'

Destination buffer too small:

Copying 10 chars of 'Hi there!!' to 10-byte buffer dest
Invalid parameter handler invoked: (L"Buffer is too small" && 0)
    new contents of dest: ''

Truncation examples:

Copying 'How do you do?' to 10-byte buffer dest with truncation semantics
    new contents of dest: 'How do yo'
    truncation did occur

Copying 'Howdy.' to 10-byte buffer dest with truncation semantics
    new contents of dest: 'Howdy.'
    truncation did not occur

Secure template overload example:
Invalid parameter handler invoked: (L"Buffer is too small" && 0)
    new contents of dest: ''
```

## <a name="example"></a>Beispiel

```C
// crt_strncpy_s_2.c
// contrasts strncpy and strncpy_s

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char a[20] = "test";
   char s[20];

   // simple strncpy usage:

   strcpy_s( s, 20, "dogs like cats" );
   printf( "Original string:\n   '%s'\n", s );

   // Here we can't use strncpy_s since we don't
   // want null termination
   strncpy( s, "mice", 4 );
   printf( "After strncpy (no null-termination):\n   '%s'\n", s );
   strncpy( s+5, "love", 4 );
   printf( "After strncpy into middle of string:\n   '%s'\n", s );

   // If we use strncpy_s, the string is terminated
   strncpy_s( s, _countof(s), "mice", 4 );
   printf( "After strncpy_s (with null-termination):\n   '%s'\n", s );

}
```

```Output
Original string:
   'dogs like cats'
After strncpy (no null-termination):
   'mice like cats'
After strncpy into middle of string:
   'mice love cats'
After strncpy_s (with null-termination):
   'mice'
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[strcat_s, wcscat_s, _mbscat_s](strcat-s-wcscat-s-mbscat-s.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
