---
title: _mbsnbcat_s, _mbsnbcat_s_l
ms.date: 11/04/2016
apiname:
- _mbsnbcat_s_l
- _mbsnbcat_s
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
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
ms.openlocfilehash: d7e7a9d121336486e590ca3bd9e3967b02a2df08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331520"
---
# <a name="mbsnbcats-mbsnbcatsl"></a>_mbsnbcat_s, _mbsnbcat_s_l

Fügt in eine Zeichenfolge mit Multibytezeichen, höchstens die ersten **n** Byte einer anderen Multibytezeichen-Zeichenfolge. Dies sind Versionen von [_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md), enthalten aber Sicherheitserweiterungen wie unter [Sicherheitsfunktionen im CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
errno_t _mbsnbcat_s(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count
);
errno_t _mbsnbcat_s_l(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcat_s(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcat_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Auf NULL endende Multibytezielzeichenfolge.

*sizeInBytes*<br/>
Größe der *Dest* Puffers in Byte.

*src*<br/>
Auf NULL endende Multibytequellzeichenfolge.

*count*<br/>
Anzahl von Bytes aus *Src* anzufügende *Dest*.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, andernfalls ein Fehlercode.

### <a name="error-conditions"></a>Fehlerbedingungen

|**dest**|*sizeInBytes*|*src*|Rückgabewert|
|------------|-------------------|-----------|------------------|
|**NULL**|any|any|**EINVAL**|
|Beliebig|<= 0|any|**EINVAL**|
|Beliebig|any|**NULL**|**EINVAL**|

Wenn eine dieser Fehlerbedingungen auftritt, generiert die Funktion einen Fehler über ungültige Parameter, wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn der Fehler behandelt wird, gibt die Funktion **EINVAL** und **Errno** zu **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_mbsnbcat_s** Funktion hinzufügt *Dest*höchstens die ersten *Anzahl* Bytes *Src*. Wenn das Byte, die direkt das Nullzeichen in vorangeht *Dest* ist ein führendes Byte ist, wird Sie durch das anfangsbyte von überschrieben *Src*. Andernfalls das ursprüngliche Byte von *Src* überschreibt das abschließende Nullzeichen von *Dest*. Wenn ein in Nullbyte *Src* vor *Anzahl* Bytes angefügt werden, **_mbsnbcat_s** fügt alle Bytes von *Src*, bis das Null-Zeichen Zeichen. Wenn *Anzahl* ist größer als die Länge des *Src*, die Länge des *Src* dient anstelle von *Anzahl*. Die resultierende Zeichenfolge wird durch ein NULL-Zeichen beendet. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

Der Ausgabewert wird von der Einstellung beeinflusst die **LC_CTYPE** -kategorieeinstellung des Gebietsschemas, siehe [Setlocale, _wsetlocale](setlocale-wsetlocale.md) für Weitere Informationen. Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne haben die **_l** -Suffix verwenden das aktuelle Gebietsschema und diejenigen, auf denen die **_l** -Suffix verwenden stattdessen den Gebietsschemaparameter, der übergeben. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht. Die Überladungen können automatisch Rückschlüsse über die Pufferlänge ziehen, wodurch kein „size“-Argument angegeben werden muss. Zudem können sie automatisch ihre neueren und sichereren Funktionen zum Ersetzen von älteren, unsichereren Funktionen verwenden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat_s**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_s_l**|**_strncat_s_l**|**_mbsnbcat_s_l**|**_wcsncat_s_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbsnbcat_s**|\<mbstring.h>|
|**_mbsnbcat_s_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbcpy_s, _mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
