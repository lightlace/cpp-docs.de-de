---
title: mbrtowc
ms.date: 11/04/2016
apiname:
- mbrtowc
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
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: bd719e7b336333f6e06a1db9b1e34784575a1602
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331524"
---
# <a name="mbrtowc"></a>mbrtowc

Konvertieren eines Multibytezeichens im aktuellen Gebietsschema in das entsprechende Breitzeichen mit der Möglichkeit des Neustarts in der Mitte eines Multibytezeichens.

## <a name="syntax"></a>Syntax

```C
size_t mbrtowc(
   wchar_t *wchar,
   const char *mbchar,
   size_t count,
   mbstate_t *mbstate
);
```

### <a name="parameters"></a>Parameter

*wchar*<br/>
Adresse eines Breitzeichens für die konvertierten Breitzeichenfolge (Typ **"wchar_t"**). Dieser Wert kann ein NULL-Zeiger sein, wenn keine Rückgabebreitzeichen erforderlich ist.

*mbchar*<br/>
Adresse einer Sequenz von Bytes (ein Multibytezeichen).

*count*<br/>
Anzahl zu überprüfender Bytes.

*mbstate*<br/>
Zeiger auf das Konvertierungzustandsobjekt. Wenn dieser Wert ein NULL-Zeiger ist, verwendet die Funktion ein statisches internes Konvertierungszustandsobjekt. Da das interne **Mbstate_t** Objekt nicht threadsicher, es wird empfohlen, dass Sie immer Ihren eigenen übergeben *Mbstate* Argument.

## <a name="return-value"></a>Rückgabewert

Einer der folgenden Werte:

0 die nächste *Anzahl* oder weniger Bytes schließen das Multibytezeichen, die die null-Breitzeichen darstellt, die in gespeichert ist *Wchar*, wenn *Wchar* ist kein null-Zeiger.

1 bis *Anzahl*(einschließlich) der nächsten *Anzahl* oder weniger Bytes schließen ein gültiges Multibytezeichen handelt. Der zurückgegebene Wert ist die Anzahl der Bytes, die das Multybytezeichen abschließen. Das entsprechende Breitzeichen befindet sich in *Wchar*, wenn *Wchar* ist kein null-Zeiger.

("size_t") (-1) Es ist ein Codierungsfehler aufgetreten. Die nächste *Anzahl* oder weniger Bytes tragen nicht in einer vollständigen und gültigen Multibytezeichen. In diesem Fall **Errno** nastaven NA hodnotu EILSEQ und der konvertierungsumwandlungszustand in *Mbstate* ist nicht angegeben.

("size_t") (-2) Die nächste *Anzahl* Bytes tragen zu einem unvollständigen, jedoch Möglicherweisen gültigen Multibytezeichen und alle *Anzahl* Bytes wurden verarbeitet. Kein Wert befindet sich in *Wchar*, aber *Mbstate* wird aktualisiert, um die Funktion neu gestartet.

## <a name="remarks"></a>Hinweise

Wenn *Mbchar* ist ein null-Zeiger entspricht der Aufruf die Funktion:

`mbrtowc(NULL, "", 1, &mbstate)`

In diesem Fall wird der Wert der Argumente *Wchar* und *Anzahl* werden ignoriert.

Wenn *Mbchar* ist kein null-Zeiger, die Funktion überprüft *Anzahl* Bytes vom *Mbchar* um die erforderliche Anzahl von Bytes zu bestimmen, die erforderlich sind, um die nächste abzuschließen Multibytezeichen. Wenn das nächste Zeichen gültig ist, befindet sich das entsprechende Multibytezeichen in *Wchar* Wenn es sich nicht um einen null-Zeiger ist. Wenn das Zeichen ist das entsprechende null-Breitzeichen-Zeichen, den resultierenden Status der *Mbstate* wird der ursprüngliche konvertierungszustand.

Die **Mbrtowc** Funktion unterscheidet sich von [Mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) durch die neustartmöglichkeit. Der konvertierungszustand befindet sich in *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbaren Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Z. B. eine Anwendung verwendet soll **Wcsrlen** anstelle von **Wcslen** Wenn ein nachfolgender Aufruf von **Wcsrtombs** anstelle **Wcstombs**.

## <a name="example"></a>Beispiel

Konvertiert ein Multibytezeichen in das entsprechende Breitzeichen.

```cpp
// crt_mbrtowc.cpp

#include <stdio.h>
#include <mbctype.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

#define BUF_SIZE 100

int Sample(char* szIn, wchar_t* wcOut, int nMax)
{
    mbstate_t   state = {0}; // Initial state
    size_t      nConvResult,
                nmbLen = 0,
                nwcLen = 0;
    wchar_t*    wcCur = wcOut;
    wchar_t*    wcEnd = wcCur + nMax;
    const char* mbCur = szIn;
    const char* mbEnd = mbCur + strlen(mbCur) + 1;
    char*       szLocal;

    // Sets all locale to French_Canada.1252
    szLocal = setlocale(LC_ALL, "French_Canada.1252");
    if (!szLocal)
    {
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");
        return 1;
    }

    printf("Locale set to: \"%s\"\n", szLocal);

    // Sets the code page associated current locale's code page
    // from a previous call to setlocale.
    if (_setmbcp(_MB_CP_SBCS) == -1)
    {
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");
        return 1;
    }

    while ((mbCur < mbEnd) && (wcCur < wcEnd))
    {
        //
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);
        switch (nConvResult)
        {
            case 0:
            {  // done
                printf("Conversion succeeded!\nMultibyte String: ");
                printf(szIn);
                printf("\nWC String: ");
                wprintf(wcOut);
                printf("\n");
                mbCur = mbEnd;
                break;
            }

            case -1:
            {  // encoding error
                printf("The call to mbrtowc has detected an encoding error.\n");
                mbCur = mbEnd;
                break;
            }

            case -2:
            {  // incomplete character
                if   (!mbsinit(&state))
                {
                    printf("Currently in middle of mb conversion, state = %x\n", state);
                    // state will contain data regarding lead byte of mb character
                }

                ++nmbLen;
                ++mbCur;
                break;
            }

            default:
            {
                if   (nConvResult > 2) // The multibyte should never be larger than 2
                {
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);
                }

                ++nmbLen;
                ++nwcLen;
                ++wcCur;
                ++mbCur;
            break;
            }
        }
    }

   return 0;
}

int main(int argc, char* argv[])
{
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";
    wchar_t wcBuf[BUF_SIZE] = {L''};

    return Sample(mbBuf, wcBuf, BUF_SIZE);
}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
