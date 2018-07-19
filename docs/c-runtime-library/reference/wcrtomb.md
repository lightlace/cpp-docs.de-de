---
title: wcrtomb | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcrtomb
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
- wcrtomb
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eca27e81cbb1df26d04059974cdc1ce5313bafa3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412676"
---
# <a name="wcrtomb"></a>wcrtomb

Konvertieren von Breitzeichen in die Multibyte-Zeichendarstellung. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [wcrtomb_s](wcrtomb-s.md).

## <a name="syntax"></a>Syntax

```C
size_t wcrtomb(
   char *mbchar,
   wchar_t wchar,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcrtomb(
   char (&mbchar)[size],
   wchar_t wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parameter

*mbchar*<br/>
Das resultierende in Multibyte konvertierte Zeichen.

*wchar*<br/>
Ein zu konvertierendes Breitzeichen.

*mbstate*<br/>
Ein Zeiger auf ein **Mbstate_t** Objekt.

## <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Bytes zurück, die erforderlich sind, um das konvertierte Multibytezeichen darzustellen, oder andernfalls -1, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Die **Wcrtomb** -Funktion konvertiert ein Breitzeichen, ab der angegebenen konvertierungszustand in enthaltenen *Mbstate*, aus dem Wert in *Wchar*, in der Adresse dargestellte *Mbchar*. Der Rückgabewert ist die Anzahl der Bytes, die erforderlich sind, um das entsprechende Multibytezeichen darzustellen, aber wird nicht zurückgegeben, mehr als **MB_CUR_MAX** Bytes.

Wenn *Mbstate* null ist, die interne **Mbstate_t** Objekt, das den konvertierungszustand der enthält *Mbchar* verwendet wird. Wenn die Zeichensequenz *Wchar* verfügt nicht über eine entsprechende Multibyte zeichendarstellung, wird-1 zurückgegeben und die **Errno** festgelegt ist, um **EILSEQ**.

Die **Wcrtomb** -Funktion unterscheidet sich von [Wctomb _wctomb_l](wctomb-wctomb-l.md) durch die neustartmöglichkeit. Der konvertierungszustand wird gespeichert, *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbarer Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Eine Anwendung verwenden z. B. **Wcsrlen** statt **Wcsnlen**, wenn ein nachfolgender Aufruf von **Wcsrtombs** verwendet wurden, anstelle von **Wcstombs**.

In C++ hat diese Funktion eine Vorlagenüberladung, mit der die neuere, sichere Entsprechung dieser Funktion aufgerufen wird. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Ausnahmen

Die **Wcrtomb** -Funktion ist multithreadsicher ist, solange keine Funktion im aktuellen Thread ruft **Setlocale** während diese Funktion ausgeführt wird und während der *Mbstate* ist null.

## <a name="example"></a>Beispiel

```C
// crt_wcrtomb.c
// compile with: /W3
// This program converts a wide character
// to its corresponding multibyte character.

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    size_t      sizeOfCovertion = 0;
    mbstate_t   mbstate;
    char        mbStr = 0;
    wchar_t*    wcStr = L"Q";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead
    if (sizeOfCovertion > 0)
    {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wcStr);
        printf(" was converted to the \"%c\" ", mbStr);
        printf("multibyte character.\n");
    }
    else
    {
        printf("No corresponding multibyte character "
               "was found.\n");
    }
}
```

```Output
The corresponding wide character "Q" was converted to the "Q" multibyte character.
```

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
