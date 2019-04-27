---
title: wctob
ms.date: 11/04/2016
apiname:
- wctob
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
- wctob
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
ms.openlocfilehash: 1d9dca16ca905afbc94d912a8083017ba9cc84e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188531"
---
# <a name="wctob"></a>wctob

Bestimmt, ob ein Breitzeichen einem Multibytezeichen entspricht und gibt dessen Multibytezeichen-Darstellung zurück.

## <a name="syntax"></a>Syntax

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>Parameter

*wchar*<br/>
Zu übersetzender Wert.

## <a name="return-value"></a>Rückgabewert

Wenn **Wctob** erfolgreich konvertiert ein Breitzeichen ist, wird dessen Multibytezeichen-Darstellung nur dann, wenn das Multibytezeichen genau ein Byte lang ist. Wenn **Wctob** entdeckt ein Breitzeichen in Multibytezeichen oder das Multibytezeichen konvertiert werden kann ist nicht genau ein Byte lang ist, wird-1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Wctob** -Funktion konvertiert ein Breitzeichen ist, die in enthaltenen *Wchar* in das entsprechende Multibytezeichen, die durch den Rückgabetyp übergeben **Int** Wert, wenn die Multibyte Zeichen ist genau ein Byte lang.

Wenn **Wctob** nicht erfolgreich war und kein entsprechendes Multibytezeichen gefunden wurde, wird die Funktion legt **Errno** zu **EILSEQ** und gibt-1 zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**wctob**|\<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Programm stellt das Verhalten der **Wcstombs** Funktion.

```C
// crt_wctob.c
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    int     bChar = 0;
    wint_t  wChar = 0;

    // Set the corresponding wide character to exactly one byte.
    wChar = (wint_t)'A';

    bChar = wctob( wChar );
    if (bChar == WEOF)
    {
        printf( "No corresponding multibyte character was found.\n");
    }
    else
    {
        printf( "Determined the corresponding multibyte character to"
                " be \"%c\".\n", bChar);
    }
}
```

```Output
Determined the corresponding multibyte character to be "A".
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
