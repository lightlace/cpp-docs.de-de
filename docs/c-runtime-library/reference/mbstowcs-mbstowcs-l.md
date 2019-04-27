---
title: mbstowcs, _mbstowcs_l
ms.date: 11/04/2016
apiname:
- mbstowcs
- _mbstowcs_l
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
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- mbstowcs
helpviewer_keywords:
- _mbstowcs_l function
- mbstowcs_l function
- mbstowcs function
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
ms.openlocfilehash: b9178f64dd698ff517ea5b376ed19e97981c511d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156654"
---
# <a name="mbstowcs-mbstowcsl"></a>mbstowcs, _mbstowcs_l

Konvertiert eine Multibyte-Zeichensequenz in eine entsprechende Breitzeichensequenz. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_mbsnbcpy_s, _mbsnbcpy_s_l](mbstowcs-s-mbstowcs-s-l.md).

## <a name="syntax"></a>Syntax

```C
size_t mbstowcs(
   wchar_t *wcstr,
   const char *mbstr,
   size_t count
);
size_t _mbstowcs_l(
   wchar_t *wcstr,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
size_t mbstowcs(
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
size_t _mbstowcs_l(
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*wcstr*<br/>
Die Adresse einer Breitzeichensequenz.

*mbstr*<br/>
Adresse einer Multibyte-Zeichensequenz.

*count*<br/>
Die maximale Anzahl zu konvertierender Multibytezeichen.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Wenn **Mbstowcs** die Quellzeichenfolge erfolgreich konvertiert wird, dass die Anzahl von konvertierten Multibytezeichen. Wenn die *Wcstr* Argument **NULL**, die Funktion gibt die erforderliche Größe (in Breitzeichen), der die Zielzeichenfolge zurück. Wenn **Mbstowcs** ein ungültiges Multibytezeichen erkennt, wird-1 zurückgegeben. Wenn der Rückgabewert ist *Anzahl*, die Breitzeichen-Zeichenfolge ist kein Null-terminiert.

> [!IMPORTANT]
> Sicherstellen, dass *Wcstr* und *Mbstr* nicht überlappen und dass *Anzahl* die Anzahl zu konvertierendermultibytezeichen korrekt darstellt.

## <a name="remarks"></a>Hinweise

Die **Mbstowcs** -Funktion konvertiert wird, bis eine maximale Anzahl von *Anzahl* Multibytezeichen verweist *Mbstr* in eine entsprechende Breitzeichenfolge, die Zeichenfolge durch das aktuelle Gebietsschema bestimmt. Sie speichert die resultierende Breitzeichen-Zeichenfolge an der Adresse durch dargestellt *Wcstr*. Das Ergebnis ähnelt einer Reihe von Aufrufen an [Mbtowc](mbtowc-mbtowc-l.md). Wenn **Mbstowcs** das Einzelbyte-Null-Zeichen ('\0') erkennt, entweder vor oder bei *Anzahl* auftritt, konvertiert der Null-Zeichen, ein Breitzeichen Null-Zeichen (L '\0') und beenden. Daher wird die Breitzeichen-Zeichenfolge an *Wcstr* ist Null-terminierte nur dann, wenn ein Null-Zeichen, die während der Konvertierung erkannt wird. Wenn die Sequenzen, zeigt *Wcstr* und *Mbstr* überlappen, ist das Verhalten nicht definiert.

Wenn die *Wcstr* Argument **NULL**, **Mbstowcs** gibt die Anzahl der Breitzeichen, die von der Konvertierung, einschließlich nicht auf einen null-Terminator führen würden. Die Quellzeichenfolge muss auf NULL enden, damit der korrekte Wert zurückgegeben wird. Wenn Sie wollen, dass die resultierende Breitzeichenfolge auf NULL endet, fügen Sie dem Rückgabewert 1 hinzu.

Wenn die *Mbstr* Argument ist **NULL**, oder wenn *Anzahl* ist > **INT_MAX**, Handler für ungültige Parameter aufgerufen, siehe [ Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die weitere Ausführung zugelassen wird, wird Errno auf festgelegt **EINVAL** und die Funktion gibt-1 zurück.

**Mbstowcs** verwendet das aktuelle Gebietsschema für jedes vom Gebietsschema abhängige Verhalten; **_mbstowcs_l** ist identisch, außer dass sie das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**mbstowcs**|\<stdlib.h>|
|**_mbstowcs_l**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_mbstowcs.c
// compile with: /W3
// illustrates the behavior of the mbstowcs function

#include <stdlib.h>
#include <stdio.h>
#include <locale.h>

int main( void )
{
    size_t size;
    int nChar = 2; // number of characters to convert
    int requiredSize;

    unsigned char    *pmbnull  = NULL;
    unsigned char    *pmbhello = NULL;
    char* localeInfo;

    wchar_t *pwchello = L"\x3042\x3043"; // 2 Hiragana characters
    wchar_t *pwc;

    /* Enable the Japanese locale and codepage */
    localeInfo = setlocale(LC_ALL, "Japanese_Japan.932");
    printf("Locale information set to %s\n", localeInfo);

    printf( "Convert to multibyte string:\n" );

    requiredSize = wcstombs( NULL, pwchello, 0); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s
    printf("   Required Size: %d\n", requiredSize);

    /* Add one to leave room for the null terminator. */
    pmbhello = (unsigned char *)malloc( requiredSize + 1);
    if (! pmbhello)
    {
        printf("Memory allocation failure.\n");
        return 1;
    }
    size = wcstombs( pmbhello, pwchello, requiredSize + 1); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s
    if (size == (size_t) (-1))
    {
        printf("Couldn't convert string. Code page 932 may"
                " not be available.\n");
        return 1;
    }
    printf( "   Number of bytes written to multibyte string: %u\n",
            (unsigned int) size );
    printf( "   Hex values of the" );
    printf( " multibyte characters: %#.2x %#.2x %#.2x %#.2x\n",
            pmbhello[0], pmbhello[1], pmbhello[2], pmbhello[3] );
    printf( "   Codepage 932 uses 0x81 to 0x9f as lead bytes.\n\n");

    printf( "Convert back to wide-character string:\n" );

    /* Assume we don't know the length of the multibyte string.
     Get the required size in characters, and allocate enough space. */

    requiredSize = mbstowcs(NULL, pmbhello, 0); // C4996
    /* Add one to leave room for the null terminator */
    pwc = (wchar_t *)malloc( (requiredSize + 1) * sizeof( wchar_t ));
    if (! pwc)
    {
        printf("Memory allocation failure.\n");
        return 1;
    }
    size = mbstowcs( pwc, pmbhello, requiredSize + 1); // C4996
    if (size == (size_t) (-1))
    {
       printf("Couldn't convert string--invalid multibyte character.\n");
    }
    printf( "   Characters converted: %u\n", (unsigned int)size );
    printf( "   Hex value of first 2" );
    printf( " wide characters: %#.4x %#.4x\n\n", pwc[0], pwc[1] );
    free(pwc);
    free(pmbhello);
}
```

```Output
Locale information set to Japanese_Japan.932
Convert to multibyte string:
   Required Size: 4
   Number of bytes written to multibyte string: 4
   Hex values of the  multibyte characters: 0x82 0xa0 0x82 0xa1
   Codepage 932 uses 0x81 to 0x9f as lead bytes.

Convert back to wide-character string:
   Characters converted: 2
   Hex value of first 2 wide characters: 0x3042 0x3043
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
