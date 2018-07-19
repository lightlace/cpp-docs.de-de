---
title: _mbsnbcat, _mbsnbcat_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbcat_l
- _mbsnbcat
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
apitype: DLLExport
f1_keywords:
- mbsnbcat
- mbsnbcat_l
- _mbsnbcat
- _mbsnbcat_l
dev_langs:
- C++
helpviewer_keywords:
- tcsncat_l function
- _tcsncat function
- mbsnbcat_l function
- mbsnbcat function
- _mbsnbcat_l function
- _tcsncat_l function
- _mbsnbcat function
- tcsncat function
ms.assetid: aa0f1d30-0ddd-48d1-88eb-c6884b20fd91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff7dc09e4305c16ebe710cb99c9e1bdd24490761
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405055"
---
# <a name="mbsnbcat-mbsnbcatl"></a>_mbsnbcat, _mbsnbcat_l

Fügt höchstens die ersten **n** Bytes einer Multibyte-Zeichenfolge in eine andere. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_mbsnbcat_s, _mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md).

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
unsigned char *_mbsnbcat(
   unsigned char *dest,
   const unsigned char *src,
   size_t count
);
unsigned char *_mbsnbcat_l(
   unsigned char *dest,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
unsigned char *_mbsnbcat(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsnbcat_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Auf NULL endende Multibytezielzeichenfolge.

*src*<br/>
Auf NULL endende Multibytequellzeichenfolge.

*count*<br/>
Anzahl der Bytes vom *Src* zum Anfügen an *Dest*.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_mbsnbcat** gibt einen Zeiger zur Zielzeichenfolge zurück. Kein Rückgabewert ist zur Fehleranzeige reserviert.

## <a name="remarks"></a>Hinweise

Die **_mbsnbcat** -Funktion fügt höchstens die ersten *Anzahl* Bytes *Src* auf *Dest*. Wenn das Byte direkt vor dem Nullzeichen in *Dest* ist ein führendes Byte ist, das ursprüngliche Byte von *Src* überschreibt dieses führende Byte. Andernfalls das ursprüngliche Byte von *Src* überschreibt das abschließende Nullzeichen von *Dest*. Wenn ein in Nullbyte *Src* vor *Anzahl* Bytes angefügt werden, **_mbsnbcat** fügt alle Bytes von *Src*, bis zu dem Null-Zeichen. Wenn *Anzahl* ist größer als die Länge des *Src*, die Länge des *Src* wird verwendet, anstelle von *Anzahl*. Die resultierende Zeichenfolge wird mit einem NULL-Zeichen beendet. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

Der Ausgabewert wird von der Einstellung der beeinflusst die **LC_CTYPE** -kategorieneinstellung des Gebietsschemas; Siehe [Setlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die **_mbsnbcat** Version der Funktion verwendet das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die **_mbsnbcat_l** -Version ist beinahe identisch, verwenden jedoch den Gebietsschemaparameter übergebene. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

**Sicherheitshinweis** Verwenden Sie eine mit NULL endende Zeichenfolge. Die mit NULL endende Zeichenfolge darf die Größe des Zielpuffers nicht überschreiten. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).

Wenn *Dest* oder *Src* ist **NULL**, generiert die Funktion einen Fehler über ungültige Parameter, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn der Fehler behandelt wird, gibt die Funktion **EINVAL** und legt **Errno** auf **EINVAL**.

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_l**|**_strncat_l**|**_mbsnbcat_l**|**_wcsncat_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_mbsnbcat**|\<mbstring.h>|
|**_mbsnbcat_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[_mbsnbcat_s, _mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md)<br/>
