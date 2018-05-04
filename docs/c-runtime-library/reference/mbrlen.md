---
title: mbrlen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77e5cb106a971bcaf02662bfd8459267a134173a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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
0|Das nächste *Anzahl* oder weniger Bytes schließen das Multibytezeichen, die Null-Breitzeichen darstellt.
1 bis *Count*(einschließlich)|Das nächste *Anzahl* oder weniger Bytes schließen ein gültiges Multibytezeichen handelt. Der zurückgegebene Wert ist die Anzahl der Bytes, die das Multybytezeichen abschließen.
(size_t)(-2)|Das nächste *Anzahl* Bytes tragen zu einem unvollständigen, jedoch Möglicherweisen gültigen Multibytezeichen bei und alle *Anzahl* Bytes wurden verarbeitet.
(size_t)(-1)|Es ist ein Codierungsfehler aufgetreten. Das nächste *Anzahl* oder weniger Bytes tragen nicht zu einem vollständigen und gültigen Multibytezeichen bei. In diesem Fall **Errno** auf EILSEQ und der Konvertierungsstatus festgelegt *Mbstate* ist nicht angegeben.

## <a name="remarks"></a>Hinweise

Die **Mbrlen** -Funktion prüft höchstens *Anzahl* Bytes, beginnend mit dem Byte verweist *str* um die Anzahl der Bytes zu bestimmen, die erforderlich sind, um den nächsten abzuschließen Multibytezeichen, einschließlich eventueller umschaltsequenzen. Dies entspricht dem Aufruf `mbrtowc(NULL, str, count, &mbstate)` , in denen *Mbstate* ist entweder eine vom Benutzer bereitgestellte **Mbstate_t** Objekt oder ein statisches internes Objekt von der Bibliothek bereitgestellt.

Die **Mbrlen** -Funktion speichert und verwendet Umschaltzustand eines unvollständigen multibytezeichens in der *Mbstate* Parameter. Dies ermöglicht **Mbrlen** die Möglichkeit des Neustarts in der Mitte eines multibytezeichens, wenn sein muss, untersuchen höchstens *Anzahl* Bytes. Wenn *Mbstate* ist ein null-Zeiger **Mbrlen** verwendet ein internes, statisches **Mbstate_t** Objekt zum Speichern des umschaltzustands. Da das interne **Mbstate_t** -Objekt nicht threadsicher, es wird empfohlen, dass Sie immer zuordnen, und übergeben Ihren eigenen *Mbstate* Parameter.

Die **Mbrlen** -Funktion unterscheidet sich von [_mbclen, Mblen, _mblen_l](mbclen-mblen-mblen-l.md) durch die neustartmöglichkeit. Der Umschaltzustand wird gespeichert, *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbarer Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Eine Anwendung sollte verwenden, z. B. **Wcsrlen** anstelle von **Wcslen** Wenn ein nachfolgender Aufruf von **Wcsrtombs** anstelle von **Wcstombs**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|Nicht zutreffend|Nicht zutreffend|**mbrlen**|Nicht zutreffend|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie die Interpretation von Multibytezeichen hängt von der aktuellen Codepage, und zeigt die Funktion zum Fortsetzen des **Mbrlen**.

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
