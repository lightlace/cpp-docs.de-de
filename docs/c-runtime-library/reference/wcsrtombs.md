---
title: wcsrtombs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcsrtombs
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
- wcsrtombs
dev_langs:
- C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2ea0252714803fe8cad48635486d2011275407
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="wcsrtombs"></a>wcsrtombs

Konvertieren von Breitzeichen in die Multibyte-Zeichenfolgendarstellung. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [wcsrtombs_s](wcsrtombs-s.md).

## <a name="syntax"></a>Syntax

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parameter

*mbstr*<br/>
Der Adressspeicherort der resultierenden konvertierten Multibyte-Zeichenfolge.

*wcstr*<br/>
Indirekter Zeiger auf den Speicherort der Breitzeichenfolge, die konvertiert werden soll.

*count*<br/>
Die Anzahl der zu konvertierenden Zeichen.

*mbstate*<br/>
Ein Zeiger auf ein **Mbstate_t** konvertierungszustandsobjekt.

## <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der erfolgreich konvertierten Bytes zurück, wobei das abschließende NULL-Byte (falls vorhanden) nicht eingeschlossen ist. Andernfalls wird bei einem Fehler -1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **Wcsrtombs** -Funktion konvertiert eine Zeichenfolge mit Breitzeichen, ab der angegebenen konvertierungszustand in enthaltenen *Mbstate*, aus den Werten, die indirekt auf das gezeigt *Wcstr*, in die Adresse des *Mbstr*. Die Konvertierung wird für jedes Zeichen bis fortgesetzt: Nachdem eine Null-Breitzeichen beendet gefunden wird, wenn ein nicht entsprechenden Zeichen erkannt wird, oder wenn das nächste Zeichen der in enthaltenen-Grenzwert übersteigen würde *Anzahl*. Wenn **Wcsrtombs** das Nullzeichen Breitzeichen (L '\0') erkennt, entweder vor oder bei *Anzahl* auftritt, konvertiert es in eine 8-Bit 0 und wird beendet.

Daher die Multibyte-Zeichenfolge am *Mbstr* ist Null-terminierte nur, wenn **Wcsrtombs** trifft eine Breitzeichen-Null-Zeichen bei der Konvertierung. Wenn die Sequenzen auf verweist *Wcstr* und *Mbstr* überlappen, ist das Verhalten des **Wcsrtombs** ist nicht definiert. **Wcsrtombs** wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.

Die **Wcsrtombs** -Funktion unterscheidet sich von [Wcstombs _wcstombs_l](wcstombs-wcstombs-l.md) durch die neustartmöglichkeit. Der konvertierungszustand wird gespeichert, *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbarer Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Eine Anwendung verwenden z. B. **Wcsrlen** statt **Wcsnlen**, wenn ein nachfolgender Aufruf von **Wcsrtombs** verwendet wurden, anstelle von **Wcstombs**.

Wenn die *Mbstr* Argument ist **NULL**, **Wcsrtombs** gibt die erforderliche Größe in Bytes, der die Zielzeichenfolge zurück. Wenn *Mbstate* null ist, wird das interne **Mbstate_t** konvertierungszustand verwendet wird. Wenn die Zeichensequenz *Wchar* verfügt nicht über eine entsprechende Multibyte zeichendarstellung, wird-1 zurückgegeben und die **Errno** festgelegt ist, um **EILSEQ**.

In C++ hat diese Funktion eine Vorlagenüberladung, mit der die neuere, sichere Entsprechung dieser Funktion aufgerufen wird. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Ausnahmen

Die **Wcsrtombs** -Funktion ist multithreadsicher ist, solange keine Funktion im aktuellen Thread ruft **Setlocale** während der Ausführung von dieser Funktion und die *Mbstate* ist ungleich null.

## <a name="example"></a>Beispiel

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
