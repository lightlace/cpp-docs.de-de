---
title: wcrtomb_s
ms.date: 11/04/2016
apiname:
- wcrtomb_s
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
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: 7fe7fba861eecec562928cf381973f62a4db60fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155471"
---
# <a name="wcrtombs"></a>wcrtomb_s

Konvertieren von Breitzeichen in die Multibyte-Zeichendarstellung. Eine Version von [wcrtomb](wcrtomb.md) mit Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char *mbchar,
   size_t sizeOfmbchar,
   wchar_t *wchar,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char (&mbchar)[size],
   wchar_t *wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parameter

*pReturnValue*<br/>
Gibt die Anzahl geschriebener Bytes oder „-1“ bei einem Fehler zurück.

*mbchar*<br/>
Das resultierende in Multibyte konvertierte Zeichen.

*sizeOfmbchar*<br/>
Die Größe der *Mbchar* -Variable in Bytes.

*wchar*<br/>
Ein zu konvertierendes Breitzeichen.

*mbstate*<br/>
Ein Zeiger auf ein **Mbstate_t** Objekt.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) oder ein **Errno** -Wert, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Die **Wcrtomb_s** -Funktion konvertiert ein Breitzeichen, beginnend beim angegebenen Konvertierungsstatus, der in enthaltenen *Mbstate*, aus dem Wert, der in enthaltenen *Wchar*, in der Adresse dargestellt werden, indem *Mbchar*. Die *pReturnValue* Wert werden die Anzahl der Bytes, die konvertiert wird, aber nicht mehr als **MB_CUR_MAX** Bytes oder-1 bei einem Fehler.

Wenn *Mbstate* null ist, die interne **Mbstate_t** konvertierungszustand wird verwendet. Wenn das Zeichen in enthalten *Wchar* verfügt nicht über ein entsprechendes Multibytezeichen, den Wert der *pReturnValue* beträgt-1, und die Funktion gibt die **Errno** Wert des **EILSEQ**.

Die **Wcrtomb_s** Funktion unterscheidet sich von [Wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md) durch die neustartmöglichkeit. Der konvertierungszustand befindet sich in *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbaren Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Eine Anwendung verwendet z. B. **Wcsrlen** statt **Wcslen**, wenn ein nachfolgender Aufruf von **Wcsrtombs_s** verwendet wurden, anstelle von **Wcstombs_s**.

In C++ wird die Verwendung dieser Funktion durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Ausnahmen

Die **Wcrtomb_s** -Funktion ist multithreadsicher, solange keine Funktion im aktuellen Thread ruft **Setlocale** während diese Funktion ausgeführt wird und die *Mbstate* ist null.

## <a name="example"></a>Beispiel

```C
// crt_wcrtomb_s.c
// This program converts a wide character
// to its corresponding multibyte character.
//

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    errno_t     returnValue;
    size_t      pReturnValue;
    mbstate_t   mbstate;
    size_t      sizeOfmbStr = 1;
    char        mbchar = 0;
    wchar_t*    wchar = L"Q\0";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),
                            *wchar, &mbstate);
    if (returnValue == 0) {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wchar);
        printf(" was converted to a the \"%c\" ", mbchar);
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
The corresponding wide character "Q" was converted to a the "Q" multibyte character.
```

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
