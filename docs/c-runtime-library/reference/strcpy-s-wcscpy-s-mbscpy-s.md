---
title: strcpy_s, wcscpy_s, _mbscpy_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/22/2086
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcscpy_s
- _mbscpy_s
- strcpy_s
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
- strcpy_s
- _mbscpy_s
- _tcscpy_s
- wcscpy_s
dev_langs:
- C++
helpviewer_keywords:
- strcpy_s function
- _tcscpy_s function
- _mbscpy_s function
- copying strings
- strings [C++], copying
- tcscpy_s function
- wcscpy_s function
ms.assetid: 611326f3-7929-4a5d-a465-a4683af3b053
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee648776d4c8b7df1089edf34d30b5c7e59a63c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416611"
---
# <a name="strcpys-wcscpys-mbscpys"></a>strcpy_s, wcscpy_s, _mbscpy_s

Kopiert eine Zeichenfolge. Diese Versionen von [strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

> [!IMPORTANT]
> **_mbscpy_s** kann nicht in Anwendungen, die in der Windows-Runtime ausgeführt verwendet werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
errno_t strcpy_s(
   char *dest,
   rsize_t dest_size,
   const char *src
);
errno_t wcscpy_s(
   wchar_t *dest,
   rsize_t dest_size,
   const wchar_t *src
);
errno_t _mbscpy_s(
   unsigned char *dest,
   rsize_t dest_size,
   const unsigned char *src
);
```

```cpp
// Template functions are C++ only:
template <size_t size>
errno_t strcpy_s(
   char (&dest)[size],
   const char *src
); // C++ only
template <size_t size>
errno_t wcscpy_s(
   wchar_t (&dest)[size],
   const wchar_t *src
); // C++ only
template <size_t size>
errno_t _mbscpy_s(
   unsigned char (&dest)[size],
   const unsigned char *src
); // C++ only
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Speicherort des Zielzeichenfolgenpuffers.

*dest_size*<br/>
Größe des zielzeichenfolgenpuffers in **Char** Einheiten für schmale und Multi-Byte-Funktionen und **Wchar_t** Einheiten für große Funktionen. Dieser Wert muss größer als 0 (null) und nicht größer als **RSIZE_MAX**.

*src*<br/>
Auf NULL endender Quellzeichenfolgepuffer.

## <a name="return-value"></a>Rückgabewert

Null (0), wenn erfolgreich; andernfalls ein Fehler.

### <a name="error-conditions"></a>Fehlerbedingungen

|*dest*|*dest_size*|*src*|Rückgabewert|Inhalt der *Dest*|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL**|alle|alle|**EINVAL**|nicht geändert|
|alle|alle|**NULL**|**EINVAL**|*Dest*[0] auf 0 festgelegt|
|alle|0 oder zu klein|alle|**ERANGE**|*Dest*[0] auf 0 festgelegt|

## <a name="remarks"></a>Hinweise

Die **Strcpy_s** Funktion übernimmt den Inhalt in die Adresse des *Src*, einschließlich des abschließenden Null-Zeichens zu dem Speicherort, der von angegeben wird *Dest*. Die Zielzeichenfolge muss groß genug sein, um die Quellzeichenfolge und ihr beendendes NULL-Zeichen zu enthalten. Das Verhalten des **Strcpy_s** ist undefiniert, wenn die Quell- und Zielzeichenfolgen überlappen.

**Wcscpy_s** ist die Breitzeichen-Version des **Strcpy_s**, und **_mbscpy_s** ist die Multibyte-Zeichenfolgen-Version. Die Argumente der **Wcscpy_s** sind Breitzeichen-Zeichenfolgen, die von **_mbscpy_s** sind Multibyte Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.

Wenn *Dest* oder *Src* ein null-Zeiger ist oder wenn das Ziel Größe Zeichenfolge *Dest_size* zu klein ist, wird der Handler für ungültige Parameter aufgerufen, wie beschrieben in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **EINVAL** und **Errno** auf **EINVAL** Wenn *Dest* oder  *Src* ein null-Zeiger ist, und sie zurückgeben **ERANGE** und **Errno** auf **ERANGE** Wenn die Zielzeichenfolge zu klein ist.

Nach erfolgreicher Ausführung endet die Zielzeichenfolge immer auf NULL.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen, wodurch kein Größenargument mehr angegeben werden muss, und sie können automatisch die älteren, weniger sicheren Funktionen durch ihre neueren, sichereren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Bibliothek Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFE". Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscpy_s**|**strcpy_s**|**_mbscpy_s**|**wcscpy_s**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**strcpy_s**|\<string.h>|
|**wcscpy_s**|\<string.h> oder \<wchar.h>|
|**_mbscpy_s**|\<mbstring.h>|

Diese Funktionen sind Microsoft-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Im Gegensatz zu Quality Produktionscode ruft in diesem Beispiel die sichere Zeichenfolge-Funktionen, ohne auf Fehler überprüft:

```C
// crt_strcpy_s.c
// Compile by using: cl /W4 crt_strcpy_s.c
// This program uses strcpy_s and strcat_s
// to build a phrase.

#include <string.h>     // for strcpy_s, strcat_s
#include <stdlib.h>     // for _countof
#include <stdio.h>      // for printf
#include <errno.h>      // for return values

int main(void)
{
    char string[80];

    strcpy_s(string, _countof(string), "Hello world from ");
    strcat_s(string, _countof(string), "strcpy_s ");
    strcat_s(string, _countof(string), "and ");
    strcat_s(string, _countof(string), "strcat_s!");

    printf("String = %s\n", string);
}
```

```Output
String = Hello world from strcpy_s and strcat_s!
```

Beim Erstellen von C++-Code möglicherweise die Vorlagenversionen einfacher zu verwenden.

```cpp
// crt_wcscpy_s.cpp
// Compile by using: cl /EHsc /W4 crt_wcscpy_s.cpp
// This program uses wcscpy_s and wcscat_s
// to build a phrase.

#include <cstring>  // for wcscpy_s, wcscat_s
#include <cstdlib>  // for _countof
#include <iostream> // for cout, includes <cstdlib>, <cstring>
#include <errno.h>  // for return values

int main(void)
{
    wchar_t string[80];
    // using template versions of wcscpy_s and wcscat_s:
    wcscpy_s(string, L"Hello world from ");
    wcscat_s(string, L"wcscpy_s ");
    wcscat_s(string, L"and ");
    // of course we can supply the size explicitly if we want to:
    wcscat_s(string, _countof(string), L"wcscat_s!");

    std::wcout << L"String = " << string << std::endl;
}
```

```Output
String = Hello world from wcscpy_s and wcscat_s!
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md) <br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md) <br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md) <br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) <br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) <br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md) <br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) <br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md) <br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
