---
title: _mbclen, mblen, _mblen_l, _mbclen_l
ms.date: 01/22/2019
api_name:
- _mbclen
- mblen
- _mblen_l
- _mbclen_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mblen
- ftclen
- _mbclen
- _mbclen_l
- tclen
- _ftclen
- _tclen
- mbclen
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- _mbclen_l function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
ms.openlocfilehash: 96775f513b33eb407981480c17cb609dd85383f6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952564"
---
# <a name="_mbclen-mblen-_mblen_l-_mbclen_l"></a>_mbclen, mblen, _mblen_l, _mbclen_l

Ruft die Länge ab und bestimmt die Gültigkeit eines Multibytezeichens.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
size_t _mbclen(
   const unsigned char *c
);
size_t _mbclen_l(
   unsigned char const* c,
   _locale_t locale
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Multibytezeichen.

*mbstr*<br/>
Adresse einer Multibytezeichen-Bytesequenz.

*count*<br/>
Anzahl zu überprüfender Bytes.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_mbclen** gibt 1 oder 2 zurück, je nachdem, ob das Multibytezeichen *c* 1 oder 2 Bytes lang ist. Für **_mbclen**gibt es keine Fehlerrückgabe. Wenn *mbstr* nicht **null**ist, gibt **mblen** die Länge des multibytezeichens in Byte zurück. Wenn *mbstr* **null** ist oder auf das breit Zeichen NULL zeigt, gibt **mblen** 0 zurück. Wenn das Objekt, auf das *mbstr* zeigt, kein gültiges Multibytezeichen innerhalb der ersten *count* -Zeichen bildet, gibt **mblen** -1 zurück.

## <a name="remarks"></a>Hinweise

Die **_mbclen** -Funktion gibt die Länge des multibytezeichens *c*in Byte zurück. Wenn *c* nicht auf das führende Byte eines multibytezeichens zeigt, wie durch einen impliziten **_ismbblead**-aufrufungs Wert bestimmt, ist das Ergebnis von **_mbclen** unvorhersehbar.

**mblen** gibt die Länge von *mbstr* in Byte zurück, wenn es sich um ein gültiges Multibytezeichen handelt, und bestimmt die Gültigkeit von Multibytezeichen, die der Codepage zugeordnet ist. **mblen** untersucht *Anzahl* oder weniger Bytes, die in *mbstr*enthalten sind, jedoch nicht mehr als **MB_CUR_MAX** bytes.

Der Ausgabewert wird von der **LC_CTYPE** -Kategorieeinstellung des Gebiets Schemas beeinflusst. Weitere Informationen finden Sie unter [setlocale](setlocale-wsetlocale.md) . Die Versionen dieser Funktionen ohne das **_l** -Suffix verwenden das aktuelle Gebiets Schema für dieses vom Gebiets Schema abhängige Verhalten. Die **_l** -suffixt-Versionen Verhalten sich identisch, verwenden jedoch stattdessen den übergebenen Gebiets Schema Parameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|**_mbclen**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
