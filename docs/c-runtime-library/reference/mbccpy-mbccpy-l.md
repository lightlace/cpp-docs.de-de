---
title: _mbccpy, _mbccpy_l
ms.date: 11/04/2016
apiname:
- _mbccpy
- _mbccpy_l
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
- _mbccpy
- tccpy
- ftccpy
- mbccpy
- _tccpy
- _ftccpy
helpviewer_keywords:
- _tccpy function
- _tccpy_l function
- tccpy_l function
- tccpy function
- mbccpy function
- _mbccpy_l function
- _mbccpy function
- mbccpy_l function
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
ms.openlocfilehash: 852097ebea41ef99b1a53f7bc344eb0c08911a4d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156836"
---
# <a name="mbccpy-mbccpyl"></a>_mbccpy, _mbccpy_l

Kopiert ein Multibytezeichen von einer Zeichenfolge in eine andere Zeichenfolge. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_mbccpy_s, _mbccpy_s_l](mbccpy-s-mbccpy-s-l.md).

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
void _mbccpy(
   unsigned char *dest,
   const unsigned char *src
);
void _mbccpy_l(
   unsigned char *dest,
   const unsigned char *src,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Kopierziel.

*src*<br/>
Zu kopierendes Multibytezeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="remarks"></a>Hinweise

Die **_mbccpy** Funktion kopiert ein Multibytezeichen von *Src* zu *Dest*.

Diese Funktion überprüft ihre Parameter. Wenn **_mbccpy** einen null-Zeiger übergeben wird, für die *Dest* oder *Src*, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL**.

**_mbccpy** verwendet das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten. **_mbccpy_l** ist identisch mit **_mbccpy** mit dem Unterschied, dass **_mbccpy_l** verwendet das Gebietsschema für jedes gebietsschemaabhängige Verhalten übergeben wurde. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

**Sicherheitshinweis** Verwenden Sie eine mit NULL endende Zeichenfolge. Die mit NULL endende Zeichenfolge darf die Größe des Zielpuffers nicht überschreiten. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns). Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|**_mbccpy**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|
|**_tccpy_l**|n/v|**_mbccpy_l**|n/v|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbccpy**|\<mbctype.h>|
|**_mbccpy_l**|\<mbctype.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
