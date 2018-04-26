---
title: strcat_s, wcscat_s, _mbscat_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- strcat_s
- _mbscat_s
- wcscat_s
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
- strcat_s
- wcscat_s
- _mbscat_s
dev_langs:
- C++
helpviewer_keywords:
- wcscat_s function
- strcat_s function
- mbscat_s function
- strings [C++], appending
- _mbscat_s function
- appending strings
ms.assetid: 0f2f9901-c5c5-480b-98bc-f8f690792fc0
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04498e690749aee9938c091623ea01b5916ef6ec
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="strcats-wcscats-mbscats"></a>strcat_s, wcscat_s, _mbscat_s

Fügt eine Zeichenfolge an. Diese Versionen von [strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.

> [!IMPORTANT]
> **_mbscat_s** kann nicht in Anwendungen, die in der Windows-Runtime ausgeführt verwendet werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
errno_t strcat_s(
   char *strDestination,
   size_t numberOfElements,
   const char *strSource
);
errno_t wcscat_s(
   wchar_t *strDestination,
   size_t numberOfElements,
   const wchar_t *strSource
);
errno_t _mbscat_s(
   unsigned char *strDestination,
   size_t numberOfElements,
   const unsigned char *strSource
);
template <size_t size>
errno_t strcat_s(
   char (&strDestination)[size],
   const char *strSource
); // C++ only
template <size_t size>
errno_t wcscat_s(
   wchar_t (&strDestination)[size],
   const wchar_t *strSource
); // C++ only
template <size_t size>
errno_t _mbscat_s(
   unsigned char (&strDestination)[size],
   const unsigned char *strSource
); // C++ only
```

### <a name="parameters"></a>Parameter

*strDestination*<br/>
Auf NULL endender Zielzeichenfolgenpuffer.

*numberOfElements*<br/>
Größe des Zielzeichenfolgenpuffers.

*strSource*<br/>
Auf NULL endender Quellzeichenfolgepuffer.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.

### <a name="error-conditions"></a>Fehlerbedingungen

|*strDestination*|*numberOfElements*|*strSource*|Rückgabewert|Inhalt der *StrDestination*|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL** oder nicht abgeschlossen|alle|alle|**EINVAL**|nicht geändert|
|alle|alle|**NULL**|**EINVAL**|*StrDestination*[0] auf 0 festgelegt|
|alle|0 oder zu klein|alle|**ERANGE**|*StrDestination*[0] auf 0 festgelegt|

## <a name="remarks"></a>Hinweise

Die **Strcat_s** -Funktion fügt *StrSource* auf *StrDestination* und beendet die Ergebniszeichenfolge mit einem Null-Zeichen. Das erste Zeichen von *StrSource* überschreibt das abschließende Nullzeichen von *StrDestination*. Das Verhalten des **Strcat_s** ist undefiniert, wenn die Quell- und Zielzeichenfolgen überlappen.

Beachten Sie, dass es sich bei dem zweiten Parameter um die Gesamtgröße des Puffers handelt, nicht um die verbleibende Größe:

```C
char buf[16];
strcpy_s(buf, 16, "Start");
strcat_s(buf, 16, " End");               // Correct
strcat_s(buf, 16 - strlen(buf), " End"); // Incorrect
```

**Wcscat_s** und **_mbscat_s** sind Breitzeichen- und multibytezeichenversionen von **Strcat_s**. Die Argumente und der Rückgabewert von **Wcscat_s** sind Breitzeichen-Zeichenfolgen, die von **_mbscat_s** sind Multibyte Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.

Wenn *StrDestination* ein null-Zeiger ist oder kein Null-terminiert ist, oder wenn *StrSource* ist ein **NULL** -Zeiger ist, oder wenn die Zielzeichenfolge zu klein ist ungültige Parameter Handler aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **EINVAL** und **Errno** auf **EINVAL**.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscat_s**|**strcat_s**|**_mbscat_s**|**wcscat_s**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**strcat_s**|\<string.h>|
|**wcscat_s**|\<string.h> oder \<wchar.h>|
|**_mbscat_s**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe Codebeispiel in [strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
