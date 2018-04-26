---
title: strspn, wcsspn, _mbsspn, _mbsspn_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsspn_l
- wcsspn
- strspn
- _mbsspn
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
- _ftcsspn
- wcsspn
- _mbsspn
- _tcsspn
- strspn
dev_langs:
- C++
helpviewer_keywords:
- wcsspn function
- strings [C++], searching
- mbsspn function
- tcsspn function
- strspn function
- substrings, finding
- _mbsspn_l function
- ftcsspn function
- _mbsspn function
- _ftcsspn function
- mbsspn_l function
- _tcsspn function
ms.assetid: d077284a-809f-4068-959e-c6d6262677eb
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 616c00f1e5043788591d47fabfcbadab44dba654
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="strspn-wcsspn-mbsspn-mbsspnl"></a>strspn, wcsspn, _mbsspn, _mbsspn_l

Gibt den Index des ersten Zeichens in einer Zeichenfolge zurück, die keinem Zeichensatz angehört.

> [!IMPORTANT]
> **_mbsspn** und **_mbsspn_l** kann nicht in Anwendungen, die in der Windows-Runtime ausgeführt verwendet werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
size_t strspn(
   const char *str,
   const char *strCharSet
);
size_t wcsspn(
   const wchar_t *str,
   const wchar_t *strCharSet
);
size_t _mbsspn(
   const unsigned char *str,
   const unsigned char *strCharSet
);
size_t _mbsspn_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Zu suchende mit NULL endende Zeichenfolge.

*strCharSet*<br/>
Mit NULL endender Zeichensatz.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt einen ganzzahligen Wert, die die Länge der Teilzeichenfolge in *str* , die vollständig aus Zeichen aus *StrCharSet*. Wenn *str* beginnt mit einem Zeichen, die nicht in *StrCharSet*, gibt die Funktion 0 zurück.

## <a name="remarks"></a>Hinweise

Die **Strspn** Funktion gibt den Index des ersten Zeichens in *str* , die gehört nicht zu den Satz von Zeichen in *StrCharSet*. Die Suche umfasst keine abschließenden Nullzeichen.

**Wcsspn** und **_mbsspn** sind Breitzeichen- und multibytezeichenversionen von **Strspn**. Die Argumente der **Wcsspn** sind Breitzeichen-Zeichenfolgen, die von **_mbsspn** sind Multibyte Zeichenfolgen. **_mbsspn** überprüft die eigenen Parameter. Wenn *str* oder *StrCharSet* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **_mbspn** legt **Errno** auf **EINVAL** und gibt 0 zurück. **Strspn** und **Wcsspn** überprüfen ihre Parameter nicht. Diese drei Funktionen verhalten sich andernfalls identisch.

Der Ausgabewert wird von der Einstellung der beeinflusst die **LC_CTYPE** -kategorieneinstellung des Gebietsschemas; Siehe [Setlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsspn**|**strspn**|**_mbsspn**|**wcsspn**|
|**n/v**|**n/v**|**_mbsspn_l**|**n/v**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**strspn**|\<string.h>|
|**wcsspn**|\<string.h> oder \<wchar.h>|
|**_mbsspn**, **_mbsspn_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_strspn.c
// This program uses strspn to determine
// the length of the segment in the string "cabbage"
// consisting of a's, b's, and c's. In other words,
// it finds the first non-abc letter.
//

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[] = "cabbage";
   int  result;
   result = strspn( string, "abc" );
   printf( "The portion of '%s' containing only a, b, or c "
           "is %d bytes long\n", string, result );
}
```

```Output
The portion of 'cabbage' containing only a, b, or c is 5 bytes long
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strspnp, _wcsspnp, _mbsspnp, _mbsspnp_l](strspnp-wcsspnp-mbsspnp-mbsspnp-l.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
