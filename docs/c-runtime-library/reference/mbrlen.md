---
title: mbrlen
ms.date: 11/04/2016
apiname:
- mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: 75ae134db0e74099a9b19f4820a44a197fdfda2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438453"
---
# <a name="mbrlen"></a>mbrlen

Bestimmen der Anzahl der Bytes, die zum Ausführen eines Multibytezeichens im aktuellen Gebietsschemas erforderlich sind, mit der Möglichkeit des Neustarts in der Mitte eines Multibytezeichens.

## <a name="syntax"></a>Syntax

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Zeiger auf das nächste Byte, das in einer Multibytezeichenfolge überprüft werden soll.

*count*<br/>
Die maximale Anzahl der zu überprüfenden Bytes.

*mbstate*<br/>
Zeiger auf den aktuellen Umschaltzustand des ersten Bytes des *str*.

## <a name="return-value"></a>Rückgabewert

Einer der folgenden Werte:

|||
|-|-|
0|Die nächste *Anzahl* oder weniger Bytes schließen das Multibytezeichen, die die Null-Breitzeichen darstellt.
1 bis *Anzahl*(einschließlich)|Die nächste *Anzahl* oder weniger Bytes schließen ein gültiges Multibytezeichen handelt. Der zurückgegebene Wert ist die Anzahl der Bytes, die das Multybytezeichen abschließen.
(size_t)(-2)|Die nächste *Anzahl* Bytes tragen zu einem unvollständigen, jedoch Möglicherweisen gültigen Multibytezeichen bei und alle *Anzahl* Bytes wurden verarbeitet.
(size_t)(-1)|Es ist ein Codierungsfehler aufgetreten. Die nächste *Anzahl* oder weniger Bytes tragen nicht in einer vollständigen und gültigen Multibytezeichen. In diesem Fall **Errno** nastaven NA hodnotu EILSEQ und der konvertierungszustand in *Mbstate* ist nicht angegeben.

## <a name="remarks"></a>Hinweise

Die **Mbrlen** -Funktion prüft höchstens *Anzahl* Bytes, beginnend mit dem Byte zeigt *str* um die Anzahl von Bytes zu bestimmen, die erforderlich sind, um die nächste abzuschließen Multibytezeichen, einschließlich eventueller umschaltsequenzen. Dies entspricht dem Aufruf `mbrtowc(NULL, str, count, &mbstate)` , in denen *Mbstate* ist entweder eine vom Benutzer bereitgestellte **Mbstate_t** Objekt oder ein statisches internes Objekt von der Bibliothek bereitgestellt.

Die **Mbrlen** -Funktion speichert und verwendet Umschaltzustand eines unvollständigen multibytezeichens in die *Mbstate* Parameter. Dadurch werden **Mbrlen** die Möglichkeit, in der Mitte eines multibytezeichens neu zu starten, wenn sein muss, untersuchen höchstens *Anzahl* Bytes. Wenn *Mbstate* ist ein null-Zeiger **Mbrlen** verwendet ein internes, statisches **Mbstate_t** Objekt, das Speichern des umschaltzustands. Da das interne **Mbstate_t** Objekt nicht threadsicher, es wird empfohlen, dass Sie immer zuordnen, und übergeben Ihren eigenen *Mbstate* Parameter.

Die **Mbrlen** Funktion unterscheidet sich von [_mbclen, Mblen, _mblen_l](mbclen-mblen-mblen-l.md) durch die neustartmöglichkeit. Die UMSCHALT-Status befindet sich in *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbaren Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Z. B. eine Anwendung verwendet soll **Wcsrlen** anstelle von **Wcslen** Wenn ein nachfolgender Aufruf von **Wcsrtombs** anstelle **Wcstombs**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|Nicht zutreffend|Nicht zutreffend|**mbrlen**|Nicht zutreffend|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie die Interpretation von multibyte-Zeichensequenz hängt von der aktuellen Codepage, und zeigt die Funktion zum Fortsetzen der **Mbrlen**.

```C
// crt_mbrlen.c
// Compile by using: cl crt_mbrlen.c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

size_t Example(const char * pStr)
{
    size_t      charLen = 0;
    size_t      charCount = 0;
    mbstate_t   mbState = {0};

    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&
            charLen != (size_t)-1)
    {
        if (charLen != (size_t)-2) // if complete mbcs char,
        {
            charCount++;
        }
    }
    return (charCount);
}

int main( void )
{
    int         cp;
    size_t      charCount = 0;
    const char  *pSample =
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";

    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);

    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale
    _setmbcp(932); // and Japanese multibyte code page
    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);
}
```

```Output

Code page: 0
é╨éτé¬é╚: Shift-jis hiragana.
Character count: 29

Code page: 932
????: Shift-jis hiragana.
Character count: 25

```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
