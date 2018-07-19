---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22adcaafc54a6b086629b7b9087b7088001bba85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417753"
---
# <a name="strnlen-strnlens-wcsnlen-wcsnlens-mbsnlen-mbsnlenl-mbstrnlen-mbstrnlenl"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l

Ruft die Länge einer Zeichenfolge durch Verwendung des aktuellen oder einen übergebenen Gebietsschemas ab. Dies sind sicherere Versionen von [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md).

> [!IMPORTANT]
> **_mbsnlen**, **_mbsnlen_l**, **_mbstrnlen**, und **_mbstrnlen_l** kann nicht in Anwendungen, die in der Windows-Runtime ausgeführt verwendet werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

Diese Funktionen geben die Anzahl von Zeichen in der Zeichenfolge zurück (ohne das abschließende Nullzeichen). Es ist keine null-Abschlusszeichen innerhalb der ersten *NumberOfElements* Bytes der Zeichenfolge (oder Breitzeichen für **Wcsnlen**), klicken Sie dann *NumberOfElements* an zurückgegeben wird Geben Sie die fehlerbedingung; NULL endende Zeichenfolgen Länge, die ausschließlich haben weniger als *NumberOfElements*.

**_mbstrnlen** und **_mbstrnlen_l** geben-1 zurück, wenn die Zeichenfolge ein ungültiges Multibytezeichen enthält.

## <a name="remarks"></a>Hinweise

> [!NOTE]
> **Strnlen** ist kein Ersatz für **Strlen**; **Strnlen** dient nur zur Berechnung der Größe nicht vertrauenswürdiger eingehender Daten in einem Puffer von bekannter Größe verwendet werden – z. B. eines Netzwerkpakets. **Strnlen** berechnet die Länge jedoch nicht hinter das Ende des Puffers, wenn die Zeichenfolge keinen Terminator aufweist. In anderen Situationen verwenden **Strlen**. (Das gleiche gilt für **Wcsnlen**, **_mbsnlen**, und **_mbstrnlen**.)

Jede dieser Funktionen gibt die Anzahl der Zeichen in *str*, jedoch ohne das abschließende Nullzeichen. Allerdings **Strnlen** und **Strnlen_s** interpretieren die Zeichenfolge als Einzelbyte-Zeichenfolge und deshalb der Rückgabewert ist immer gleich der Anzahl von Bytes, auch wenn die Zeichenfolge Multibytezeichen enthält. Zeichen. **Wcsnlen** und **Wcsnlen_s** sind Breitzeichenversionen von **Strnlen** und **Strnlen_s** bzw.; die Argumente für **Wcsnlen**  und **Wcsnlen_s** sind Breitzeichen Zeichenfolgen und die zeichenzählung erfolgt in breitzeicheneinheiten. Andernfalls **Wcsnlen** und **Strnlen** Verhalten sich identisch, ebenso **Strnlen_s** und **Wcsnlen_s**.

**Strnlen**, **Wcsnlen**, und **_mbsnlen** überprüfen ihre Parameter nicht. Wenn *str* ist **NULL**, tritt eine zugriffsverletzung auf.

**Strnlen_s** und **Wcsnlen_s** überprüfen ihre Parameter. Wenn *str* ist **NULL**, die Funktionen 0 zurück.

**_mbstrnlen** auch überprüft ihre Parameter. Wenn *str* ist **NULL**, oder wenn *NumberOfElements* ist größer als **INT_MAX**, **_mbstrnlen** generiert eine Ausnahme für ungültige Parameter, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **_mbstrnlen** legt **Errno** auf **EINVAL** und gibt-1 zurück.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen** und **_mbstrnlen** Geben Sie die Anzahl von Multibytezeichen in einer Multibyte Zeichenfolge zurück. **_mbsnlen** erkennt Multibyte-Zeichenfolgen entsprechend der multibyte-Codepage, die derzeit in Verwendung oder nach der das übergebene Gebietsschema bildet testet er nicht für die Gültigkeit von Multibytezeichen. **_mbstrnlen** testet auf Gültigkeit von Multibytezeichen und erkennt Multibyte-Zeichenfolgen. Wenn die Zeichenfolge, die an **_mbstrnlen** enthält ein ungültiges Multibytezeichen **Errno** festgelegt ist, um **EILSEQ**.

Der Ausgabewert wird von der Einstellung der beeinflusst die **LC_CTYPE** -kategorieneinstellung des Gebietsschemas; Siehe [Setlocale, _wsetlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne haben die **_l** -Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängiges Verhalten und die Versionen mit dem **_l** Suffix Verwenden Sie stattdessen den Gebietsschemaparameter, der übergeben wird. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Strnlen**, **Strnlen_s**|\<string.h>|
|**Wcsnlen**, **Wcsnlen_s**|\<string.h> oder \<wchar.h>|
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
