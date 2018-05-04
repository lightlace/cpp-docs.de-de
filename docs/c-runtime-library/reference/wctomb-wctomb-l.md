---
title: wctomb, _wctomb_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wctomb_l
- wctomb
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
- wctomb
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e756ea23e32ffc9b164ccbe1a68b9fc987fe7b59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="wctomb-wctombl"></a>wctomb, _wctomb_l

Konvertiert ein Breitzeichen in das entsprechende Multibytezeichen. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md).

## <a name="syntax"></a>Syntax

```C
int wctomb(
   char *mbchar,
   wchar_t wchar
);
int _wctomb_l(
   char *mbchar,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*mbchar*<br/>
Die Adresse eines Multibytezeichens.

*wchar*<br/>
Ein Breitzeichen.

## <a name="return-value"></a>Rückgabewert

Wenn **Wctomb** konvertiert das Breitzeichen in ein Multibytezeichen gibt es die Anzahl der Bytes (also nie größer als **MB_CUR_MAX**) in der Breitzeichen. Wenn *Wchar* ist das Nullzeichen Breitzeichen (L '\0'), **Wctomb** gibt 1 zurück. Wenn die Zielzeiger *Mbchar* NULL ist, **Wctomb** gibt 0 zurück. Wenn die Konvertierung nicht möglich, im aktuellen Gebietsschema ist **Wctomb** gibt-1 zurück und **Errno** festgelegt ist, um **EILSEQ**.

## <a name="remarks"></a>Hinweise

Die **Wctomb** -Funktion konvertiert die *Wchar* Argument an das entsprechende Multibytezeichen und speichert das Ergebnis an *Mbchar*. Sie können die Funktion von einem beliebigen Punkt in einem beliebigen Programm aufrufen. **Wctomb** verwendet das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; **_wctomb_l** ist identisch mit **Wctomb** identisch, jedoch das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

**Wctomb** überprüft die eigenen Parameter. Wenn *Mbchar* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und die Funktion gibt-1 zurück.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**wctomb**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm stellt das Verhalten der Funktion „wctomb“ dar.

```cpp
// crt_wctomb.cpp
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int i;
   wchar_t wc = L'a';
   char *pmb = (char *)malloc( MB_CUR_MAX );

   printf( "Convert a wide character:\n" );
   i = wctomb( pmb, wc ); // C4996
   // Note: wctomb is deprecated; consider using wctomb_s
   printf( "   Characters converted: %u\n", i );
   printf( "   Multibyte character: %.1s\n\n", pmb );
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
