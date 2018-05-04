---
title: wctomb_s, _wctomb_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wctomb_s_l
- wctomb_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctomb_s
- _wctomb_s_l
dev_langs:
- C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb0a44414b01d0105f911732bc3dd2662a278158
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="wctombs-wctombsl"></a>wctomb_s, _wctomb_s_l

Konvertiert ein Breitzeichen in das entsprechende Multibytezeichen. Eine Version von [wctomb, _wctomb_l](wctomb-wctomb-l.md) mit Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t wctomb_s(
   int *pRetValue,
   char *mbchar,
   size_t sizeInBytes,
   wchar_t wchar
);
errno_t _wctomb_s_l(
   int *pRetValue,
   char *mbchar,
   size_t sizeInBytes,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*pRetValue*<br/>
Die Anzahl von Bytes oder ein Code, der das Ergebnis angibt.

*mbchar*<br/>
Die Adresse eines Multibytezeichens.

*sizeInBytes*<br/>
Größe des Puffers *Mbchar*.

*wchar*<br/>
Ein Breitzeichen.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, Fehlercode bei Fehler.

Fehlerbedingungen

|*mbchar*|*sizeInBytes*|Rückgabewert|*pRetValue*|
|--------------|-------------------|------------------|-----------------|
|**NULL**|>0|**EINVAL**|nicht geändert|
|alle|>**INT_MAX**|**EINVAL**|nicht geändert|
|alle|zu klein|**EINVAL**|nicht geändert|

Wenn eine der oben genannten Fehlerbedingungen auftritt, wird ein Handler für ungültige Parameter aufgerufen (siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md)). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Wctomb** gibt **EINVAL** und legt **Errno** auf **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **Wctomb_s** -Funktion konvertiert die *Wchar* Argument an das entsprechende Multibytezeichen und speichert das Ergebnis an *Mbchar*. Sie können die Funktion von einem beliebigen Punkt in einem beliebigen Programm aufrufen.

Wenn **Wctomb_s** konvertiert das Breitzeichen in ein Multibytezeichen, legt er die Anzahl der Bytes (also nie größer als **MB_CUR_MAX**) in der Breitzeichen in die Ganzzahl verweist *pRetValue*. Wenn *Wchar* ist das Nullzeichen Breitzeichen (L '\0'), **Wctomb_s** füllt *pRetValue* mit 1. Wenn die Zielzeiger *Mbchar* NULL ist, **Wctomb_s** setzt 0 in *pRetValue*. Wenn die Konvertierung nicht möglich, im aktuellen Gebietsschema ist **Wctomb_s** setzt-1 in *pRetValue*.

**Wctomb_s** verwendet das aktuelle Gebietsschema für gebietsschemaabhängige zu **_wctomb_s_l** ist nahezu identisch, das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**wctomb_s**|\<stdlib.h>|
|**_wctomb_s_l**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm veranschaulicht das Verhalten von der **Wctomb** Funktion.

```cpp
// crt_wctomb_s.cpp
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    int i;
    wchar_t wc = L'a';
    char *pmb = (char *)malloc( MB_CUR_MAX );

    printf_s( "Convert a wide character:\n" );
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );
    printf_s( "   Characters converted: %u\n", i );
    printf_s( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
