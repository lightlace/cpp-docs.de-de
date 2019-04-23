---
title: wcsrtombs_s
ms.date: 11/04/2016
apiname:
- wcsrtombs_s
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
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: bd965271a65fa91b427c7af7bbd4173b129e1d8c
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124914"
---
# <a name="wcsrtombss"></a>wcsrtombs_s

Konvertieren von Breitzeichen in die Multibyte-Zeichenfolgendarstellung. Eine Version von [wcsrtombs](wcsrtombs.md) mit Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parameter

*pReturnValue*<br/>
Die Größe in Bytes der konvertierten Zeichenfolge ist, einschließlich null-Terminator.

*mbstr*<br/>
Die Pufferadresse für die resultierende konvertierte Multibyte-Zeichenfolge.

*sizeInBytes*<br/>
Die Größe in Bytes, der die *Mbstr* Puffer.

*wcstr*<br/>
Zeigt auf die zu konvertierende Breitzeichenfolge.

*count*<br/>
Die maximale Anzahl von Bytes, die in gespeichert werden die *Mbstr* Puffer oder [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
Ein Zeiger auf ein **Mbstate_t** konvertierungszustandsobjekt.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, Fehlercode bei Fehler.

|Fehlerbedingung|Rückgabewert und **Errno**|
|---------------------|------------------------------|
|*Mbstr* ist **NULL** und *SizeInBytes* > 0|**EINVAL**|
|*Wcstr* ist **NULL**|**EINVAL**|
|Der Zielpuffer ist zu klein, um die konvertierte Zeichenfolge enthalten (es sei denn, *Anzahl* ist **_TRUNCATE**; Siehe Hinweise unten)|**ERANGE**|

Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion einen Fehlercode zurück und legt **Errno** wie in der Tabelle angegeben.

## <a name="remarks"></a>Hinweise

Die **Wcsrtombs_s** -Funktion konvertiert eine Zeichenfolge mit Breitzeichen verweist *Wcstr* in den Puffer, der auf gespeicherte Multibytezeichen *Mbstr*unter Verwendung der enthaltenen konvertierungszustand *Mbstate*. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine der folgenden Bedingungen eintritt:

- Ein Breitzeichen NULL wird erkannt.

- Ein Breitzeichen, das nicht konvertiert werden kann, wird erkannt.

- Die Anzahl der Bytes in einem der *Mbstr* Puffer ist gleich *Anzahl*.

Die Zielzeichenfolge endet immer mit NULL, selbst bei einem Fehler.

Wenn *Anzahl* der spezielle Wert [_TRUNCATE](../../c-runtime-library/truncate.md), klicken Sie dann **Wcsrtombs_s** konvertiert Anteil der Zeichenfolge wie in den Zielpuffer passt, und weiterhin Platz für ein NULL-Wert Abschlusszeichen.

Wenn **Wcsrtombs_s** die Quellzeichenfolge erfolgreich konvertiert wird die Größe in Byte der konvertierten Zeichenfolge ist, einschließlich der null-Terminator in  *&#42;pReturnValue* (bereitgestellte  *pReturnValue* nicht **NULL**). Dies tritt auf, auch wenn die *Mbstr* Argument **NULL** und bietet eine Möglichkeit, um die Größe des erforderlichen Puffers zu bestimmen. Beachten Sie, dass bei *Mbstr* ist **NULL**, *Anzahl* wird ignoriert.

Wenn **Wcsrtombs_s** findet ein Breitzeichen ist, die in einem multibyte-Zeichen konvertiert werden kann – 1 und speichert Sie im  *\*pReturnValue*, festgelegt,derZielpufferaufeineleereZeichenfolge**Errno** zu **EILSEQ**, und gibt **EILSEQ**.

Wenn die Sequenzen, zeigt *Wcstr* und *Mbstr* überlappen, ist das Verhalten der **Wcsrtombs_s** ist nicht definiert. **Wcsrtombs_s** wird von der LC_TYPE-Kategorie des aktuellen Gebietsschemas beeinflusst.

> [!IMPORTANT]
> Sicherstellen, dass *Wcstr* und *Mbstr* nicht überlappen und dass *Anzahl* die Anzahl zu konvertierender Breitzeichen korrekt darstellt.

Die **Wcsrtombs_s** Funktion unterscheidet sich von [Wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) durch die neustartmöglichkeit. Der konvertierungszustand befindet sich in *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbaren Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Eine Anwendung verwendet z. B. **Wcsrlen** statt **Wcslen**, wenn ein nachfolgender Aufruf von **Wcsrtombs_s** verwendet wurden, anstelle von **Wcstombs_s**.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Ausnahmen

Die **Wcsrtombs_s** -Funktion ist multithreadsicher, solange keine Funktion im aktuellen Thread ruft **Setlocale** während diese Funktion ausgeführt wird und die *Mbstate* ist null.

## <a name="example"></a>Beispiel

```cpp
// crt_wcsrtombs_s.cpp
//
// This code example converts a wide
// character string into a multibyte
// character string.
//

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

void main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    errno_t         err;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);
    if (err == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfully converted.\n" );
    }
}
```

```Output
The string was successfully converted.
```

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**wcsrtombs_s**|\<wchar.h>|

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
