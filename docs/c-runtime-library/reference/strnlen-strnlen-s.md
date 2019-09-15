---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
ms.date: 11/04/2016
api_name:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
ms.openlocfilehash: 6613c79bd9637b857dbf825eca2b37c71c154bec
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70947001"
---
# <a name="strnlen-strnlen_s-wcsnlen-wcsnlen_s-_mbsnlen-_mbsnlen_l-_mbstrnlen-_mbstrnlen_l"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l

Ruft die Länge einer Zeichenfolge durch Verwendung des aktuellen oder einen übergebenen Gebietsschemas ab. Dies sind sicherere Versionen von [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md).

> [!IMPORTANT]
> **_mbsnlen**, **_mbsnlen_l**, **_mbstrnlen**und **_mbstrnlen_l** können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
size_t strnlen(
   const char *str,
   size_t numberOfElements
);
size_t strnlen_s(
   const char *str,
   size_t numberOfElements
);
size_t wcsnlen(
   const wchar_t *str,
   size_t numberOfElements
);
size_t wcsnlen_s(
   const wchar_t *str,
   size_t numberOfElements
);
size_t _mbsnlen(
   const unsigned char *str,
   size_t numberOfElements
);
size_t _mbsnlen_l(
   const unsigned char *str,
   size_t numberOfElements,
   _locale_t locale
);
size_t _mbstrnlen(
   const char *str,
   size_t numberOfElements
);
size_t _mbstrnlen_l(
   const char *str,
   size_t numberOfElements,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Mit NULL endende Zeichenfolge.

*numberOfElements*<br/>
Die Größe des Zeichenfolgenpuffers.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Diese Funktionen geben die Anzahl von Zeichen in der Zeichenfolge zurück (ohne das abschließende Nullzeichen). Wenn kein NULL-Terminator in den ersten *anzahlungsbytes* der Zeichenfolge (oder breit Zeichen für **wcsnlen**) vorhanden ist, wird " *suffiofelements* " zurückgegeben, um den Fehlerzustand anzugeben. NULL-terminierte Zeichen folgen haben Längen, die streng kleiner *sind als "* ".

**_mbstrnlen** und **_mbstrnlen_l** geben-1 zurück, wenn die Zeichenfolge ein ungültiges Multibytezeichen enthält.

## <a name="remarks"></a>Hinweise

> [!NOTE]
> " **strinnlen** " ist kein Ersatz für " **straulen**". " **straunlen** " soll nur zur Berechnung der Größe eingehender, nicht vertrauenswürdiger Daten in einem Puffer der bekannten Größe verwendet werden, z. –. eines Netzwerk Pakets. " **stringenlen** " berechnet die Länge, geht jedoch nicht über das Ende des Puffers hinaus, wenn die Zeichenfolge nicht mehr ist. Verwenden Sie in anderen Situationen " **strinlen**". (Gleiches gilt für **wcsnlen**, **_mbsnlen**und **_mbstrnlen**.)

Jede dieser Funktionen gibt die Anzahl der Zeichen in *Str*zurück, ohne das abschließende Null Zeichen. Allerdings wird die Zeichenfolge von " **straunlen** " und " **Strnlen_s** " als Einzel Byte-Zeichenfolge interpretiert, sodass der Rückgabewert immer der Anzahl von Bytes entspricht, selbst wenn die Zeichenfolge Multibytezeichen enthält. **wcsnlen** und **Wcsnlen_s** sind breit Zeichen Versionen von " **strinnlen** " und " **Strnlen_s** ". die Argumente für **wcsnlen** und **Wcsnlen_s** sind breit Zeichen-Zeichen folgen, und die Anzahl der Zeichen in Einheiten mit breit Zeichen. Andernfalls Verhalten sich **wcsnlen** und **straunlen** wie **Strnlen_s** und **Wcsnlen_s**identisch.

" **strinnlen**", " **wcsnlen**" und " **_mbsnlen** " überprüfen Ihre Parameter nicht. Wenn *Str* **null**ist, tritt eine Zugriffsverletzung auf.

**Strnlen_s** und **Wcsnlen_s** überprüfen Ihre Parameter. Wenn *Str* **null**ist, geben die Funktionen 0 zurück.

**_mbstrnlen** überprüft auch seine Parameter. Wenn *Str* **null**ist, oder wenn " *numofelements* " größer als **INT_MAX**ist, generiert **_mbstrnlen** eine Ausnahme wegen eines ungültigen Parameters, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt _mbstrnlen **errno** auf **EINVAL** fest und gibt-1 zurück.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen** und **_mbstrnlen** geben die Anzahl von Multibytezeichen in einer Multibytezeichenfolge zurück. **_mbsnlen** erkennt multibytezeichensequenzen entsprechend der Multibytezeichen-Codepage, die derzeit verwendet wird, oder gemäß dem übergebenen Gebiets Schema. Er testet nicht auf die Gültigkeit von Multibytezeichen. **_mbstrnlen** testet die Gültigkeit von Multibytezeichen und erkennt multibytezeichensequenzen. Wenn die an **_mbstrnlen** über gegebene Zeichenfolge ein ungültiges Multibytezeichen enthält, wird **errno** auf **EILSEQ**festgelegt.

Der Ausgabewert wird von der Einstellung der **LC_CTYPE** -Kategorieeinstellung des Gebiets Schemas beeinflusst. Weitere Informationen finden Sie [unter setlocale, _wsetlocale](setlocale-wsetlocale.md) . Die Versionen dieser Funktionen sind identisch, außer dass diejenigen ohne das **_l** -Suffix das aktuelle Gebiets Schema für dieses vom Gebiets Schema abhängige Verhalten verwenden, und die Versionen mit dem **_l** -Suffix verwenden stattdessen den übergebenen Gebiets Schema Parameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strnlen**, **strnlen_s**|\<string.h>|
|**wcsnlen**, **Wcsnlen_s**|\<string.h> oder \<wchar.h>|
|**_mbsnlen**, **_mbsnlen_l**|\<mbstring.h>|
|**_mbstrnlen**, **_mbstrnlen_l**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_strnlen.c

#include <string.h>

int main()
{
   // str1 is 82 characters long. str2 is 159 characters long

   char* str1 = "The length of a string is the number of characters\n"
               "excluding the terminating null.";
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"
                "than the maximum size specified, the maximum size is\n"
                "returned rather than the actual size of the string.";
   size_t len;
   size_t maxsize = 100;

   len = strnlen(str1, maxsize);
   printf("%s\n Length: %d \n\n", str1, len);

   len = strnlen(str2, maxsize);
   printf("%s\n Length: %d \n", str2, len);
}
```

```Output
The length of a string is the number of characters
excluding the terminating null.
Length: 82

strnlen takes a maximum size. If the string is longer
than the maximum size specified, the maximum size is
returned rather than the actual size of the string.
Length: 100
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
