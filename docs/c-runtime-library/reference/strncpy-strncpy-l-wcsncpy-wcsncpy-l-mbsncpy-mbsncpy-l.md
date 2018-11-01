---
title: strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l
ms.date: 11/04/2016
apiname:
- strncpy
- _strncpy_l
- _mbsncpy
- wcsncpy
- _mbsncpy_l
- _wcsncpy_l
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
- _fstrncpy
- strncpy
- _ftcsncpy
- _tcsnccpy_l
- _tcsnccpy
- _mbsncpy
- wcsncpy
- _tcsncpy
- _strncpy_l
- _mbsncpy_l
- _wcsncpy_l
helpviewer_keywords:
- wcsncpy_l function
- characters [C++], copying
- mbsncpy_l function
- strncpy_l function
- wcsncpy function
- tcsnccpy function
- ftcsncpy function
- copying characters of strings
- _wcsncpy_l function
- _tcsnccpy function
- _tcsnccpy_l function
- strncpy function
- _tcsncpy function
- mbsncpy function
- _fstrncpy function
- _mbsncpy_l function
- tcsncpy_l function
- tcsnccpy_l function
- fstrncpy function
- strings [C++], copying
- _ftcsncpy function
- _tcsncpy_l function
- _mbsncpy function
- tcsncpy function
- _strncpy_l function
ms.assetid: ac4345a1-a129-4f2f-bb8a-373ec58ab8b0
ms.openlocfilehash: 5260d120fe1e5826bb4b9ebc8410a8bd1040ff3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507733"
---
# <a name="strncpy-strncpyl-wcsncpy-wcsncpyl-mbsncpy-mbsncpyl"></a>strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l

Kopieren von Zeichen aus einer Zeichenfolge in eine andere. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md).

> [!IMPORTANT]
> **_mbsncpy** und **_mbsncpy_l** kann nicht verwendet werden, in Anwendungen, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
char *strncpy(
   char *strDest,
   const char *strSource,
   size_t count
);
char *_strncpy_l(
   char *strDest,
   const char *strSource,
   size_t count,
   locale_t locale
);
wchar_t *wcsncpy(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
wchar_t *_wcsncpy_l(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count,
   locale_t locale
);
unsigned char *_mbsncpy(
   unsigned char *strDest,
   const unsigned char *strSource,
   size_t count
);
unsigned char *_mbsncpy_l(
   unsigned char *strDest,
   const unsigned char *strSource,
   size_t count,
   _locale_t locale
);
template <size_t size>
char *strncpy(
   char (&strDest)[size],
   const char *strSource,
   size_t count
); // C++ only
template <size_t size>
char *_strncpy_l(
   char (&strDest)[size],
   const char *strSource,
   size_t count,
   locale_t locale
); // C++ only
template <size_t size>
wchar_t *wcsncpy(
   wchar_t (&strDest)[size],
   const wchar_t *strSource,
   size_t count
); // C++ only
template <size_t size>
wchar_t *_wcsncpy_l(
   wchar_t (&strDest)[size],
   const wchar_t *strSource,
   size_t count,
   locale_t locale
); // C++ only
template <size_t size>
unsigned char *_mbsncpy(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsncpy_l(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*strDest*<br/>
Zielzeichenfolge.

*strSource*<br/>
Quellzeichenfolge.

*count*<br/>
Anzahl der zu kopierenden Zeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt *StrDest*. Kein Rückgabewert ist zur Fehleranzeige reserviert.

## <a name="remarks"></a>Hinweise

Die **Strncpy** Funktion übernimmt die anfänglichen *Anzahl* Zeichen *StrSource* zu *StrDest* und gibt *StrDest* . Wenn *Anzahl* ist kleiner oder gleich der Länge der *StrSource*, ein Null-Zeichen wird nicht automatisch an die kopierte Zeichenfolge angefügt. Wenn *Anzahl* ist größer als die Länge des *StrSource*, wird die Zielzeichenfolge mit Nullzeichen bis zur Länge aufgefüllt *Anzahl*. Das Verhalten der **Strncpy** ist undefiniert, wenn die Quell- und Zielzeichenfolgen überlappen.

> [!IMPORTANT]
> **Strncpy** überprüft nicht auf genügend Speicherplatz *StrDest*; dadurch eine mögliche Ursache von Pufferüberläufen. Die *Anzahl* -Argument begrenzt die Anzahl der kopierten Zeichen; es handelt es sich nicht um eine Begrenzung auf die Größe des *StrDest*. Weitere Informationen finden Sie im folgenden Beispiel. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

Wenn *StrDest* oder *StrSource* ist eine **NULL** -Zeiger ist, oder wenn *Anzahl* ist kleiner als oder gleich 0 (null), wird der Handler für ungültige Parameter aufgerufen, Siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

**Wcsncpy** und **_mbsncpy** sind Breitzeichen- und multibytezeichenversionen von Versionen von **Strncpy**. Die Argumente und der Rückgabewert von **Wcsncpy** und **_mbsncpy** unterscheiden sich entsprechend. Diese sechs Funktionen verhalten sich andernfalls identisch.

Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie das Gebietsschema für den übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten verwenden. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncpy**|**strncpy**|**_mbsnbcpy**|**wcsncpy**|
|**_tcsncpy_l**|**_strncpy_l**|**_mbsnbcpy_l**|**_wcsncpy_l**|

> [!NOTE]
> **_strncpy_l** und **_wcsncpy_l** haben keine gebietsschemaabhängigkeit; sie stehen nur für **_tcsncpy_l** und werden nicht direkt aufgerufen werden soll.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strncpy**|\<string.h>|
|**wcsncpy**|\<string.h> oder \<wchar.h>|
|**_mbsncpy**, **_mbsncpy_l**|\<mbstring.h>|

Weitere Informationen zur Plattformkompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Verwendung von **Strncpy** und wie es missbraucht werden kann, um Programmfehlern und Sicherheitsprobleme entstehen. Der Compiler generiert eine Warnung für jeden Aufruf von **Strncpy** ähnelt **crt_strncpy_x86.c(15):: Warnung C4996: 'Strncpy': Diese Funktion oder Variable ist möglicherweise unsicher. Verwenden Sie stattdessen „strncpy_s“. Zum Deaktivieren der Veraltungswarnung verwenden Sie „_CRT_SECURE_NO_WARNINGS“. Details finden Sie in der Onlinehilfe.**

```C
// crt_strncpy_x86.c
// Use this command in an x86 developer command prompt to compile:
// cl /TC /W3 crt_strncpy_x86.c

#include <stdio.h>
#include <string.h>

int main() {
   char t[20];
   char s[20];
   char *p = 0, *q = 0;

   strcpy_s(s, sizeof(s), "AA BB CC");
   // Note: strncpy is deprecated; consider using strncpy_s instead
   strncpy(s, "aa", 2);     // "aa BB CC"         C4996
   strncpy(s + 3, "bb", 2); // "aa bb CC"         C4996
   strncpy(s, "ZZ", 3);     // "ZZ",              C4996
                            // count greater than strSource, null added
   printf("%s\n", s);

   strcpy_s(s, sizeof(s), "AA BB CC");
   p = strstr(s, "BB");
   q = strstr(s, "CC");
   strncpy(s, "aa", p - s - 1);   // "aa BB CC"   C4996
   strncpy(p, "bb", q - p - 1);   // "aa bb CC"   C4996
   strncpy(q, "cc",  q - s);      // "aa bb cc"   C4996
   strncpy(q, "dd", strlen(q));   // "aa bb dd"   C4996
   printf("%s\n", s);

   // some problems with strncpy
   strcpy_s(s, sizeof(s), "test");
   strncpy(t, "this is a very long string", 20 ); // C4996
   // Danger: at this point, t has no terminating null,
   // so the printf continues until it runs into one.
   // In this case, it will print "this is a very long test"
   printf("%s\n", t);

   strcpy_s(t, sizeof(t), "dogs like cats");
   printf("%s\n", t);

   strncpy(t + 10, "to chase cars.", 14); // C4996
   printf("%s\n", t);

   // strncpy has caused a buffer overrun and corrupted string s
   printf("Buffer overrun: s = '%s' (should be 'test')\n", s);
   // Since the stack grows from higher to lower addresses, buffer
   // overruns can corrupt function return addresses on the stack,
   // which can be exploited to run arbitrary code.
}
```

Output

```Output
ZZ
aa bb dd
this is a very long test
dogs like cats
dogs like to chase cars.
Buffer overrun: s = 'ars.' (should be 'test')
```

Das Layout von automatischen Variablen und die Ebene der Fehlererkennung und der Codeschutz kann durch geänderte Compilereinstellungen variieren. Durch dieses Beispiel können sich unterschiedliche Ergebnisse ergeben, wenn es in andere Kompilierungsumgebungen oder mit anderen Compileroptionen integriert wird.

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
