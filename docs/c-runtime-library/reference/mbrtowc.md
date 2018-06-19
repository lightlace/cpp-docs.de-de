---
title: mbrtowc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 256c3df754607d0d9321f87d565e2ce94491035c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405314"
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
Die Adresse eines Breitzeichens an die konvertierten Breitzeichenfolge (Typ **Wchar_t**). Dieser Wert kann ein NULL-Zeiger sein, wenn keine Rückgabebreitzeichen erforderlich ist.

*mbchar*<br/>
Adresse einer Sequenz von Bytes (ein Multibytezeichen).

*count*<br/>
Anzahl zu überprüfender Bytes.

*mbstate*<br/>
Zeiger auf das Konvertierungzustandsobjekt. Wenn dieser Wert ein NULL-Zeiger ist, verwendet die Funktion ein statisches internes Konvertierungszustandsobjekt. Da das interne **Mbstate_t** -Objekt nicht threadsicher, es wird empfohlen, dass Sie immer eigene übergeben *Mbstate* Argument.

## <a name="return-value"></a>Rückgabewert

Einer der folgenden Werte:

0 nächsten *Anzahl* oder weniger Bytes schließen das Multibytezeichen, das das nulll-Breitzeichen darstellt, die in gespeichert ist *Wchar*, wenn *Wchar* ist ein null-Zeiger.

1 bis *Anzahl*, einschließlich der nächsten *Anzahl* oder weniger Bytes schließen ein gültiges Multibytezeichen handelt. Der zurückgegebene Wert ist die Anzahl der Bytes, die das Multybytezeichen abschließen. Das entsprechende Breitzeichen wird gespeichert, *Wchar*, wenn *Wchar* ist ein null-Zeiger.

(Size_t) (-1) Es ist ein Codierungsfehler aufgetreten. Das nächste *Anzahl* oder weniger Bytes tragen nicht zu einem vollständigen und gültigen Multibytezeichen bei. In diesem Fall **Errno** auf EILSEQ und der konvertierungsumwandlungszustand in festgelegt *Mbstate* ist nicht angegeben.

(Size_t) (-2) Das nächste *Anzahl* Bytes tragen zu einem unvollständigen, jedoch Möglicherweisen gültigen Multibytezeichen bei, und alle *Anzahl* Bytes wurden verarbeitet. Kein Wert befindet sich in *Wchar*, aber *Mbstate* wird aktualisiert, um die Funktion neu gestartet.

## <a name="remarks"></a>Hinweise

Wenn *Mbchar* ist ein null-Zeiger, die Funktion für den Aufruf entspricht:

`mbrtowc(NULL, "", 1, &mbstate)`

In diesem Fall werden die Werte der Argumente *Wchar* und *Anzahl* werden ignoriert.

Wenn *Mbchar* ist kein Nullzeiger ist, überprüft die Funktion *Anzahl* Bytes vom *Mbchar* um die erforderliche Anzahl von Bytes zu bestimmen, die erforderlich sind, um den nächsten abzuschließen Multibytezeichen. Wenn das nächste Zeichen gültig ist, wird das entsprechende Multibytezeichen gespeicherten *Wchar* , wenn es sich nicht um einen null-Zeiger ist. Wenn das Zeichen ist das entsprechende null-Breitzeichen Zeichen ist, wird den resultierenden Status der *Mbstate* wird von der ursprünglichen konvertierungszustand.

Die **Mbrtowc** -Funktion unterscheidet sich von [Mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) durch die neustartmöglichkeit. Der konvertierungszustand wird gespeichert, *Mbstate* für nachfolgende Aufrufe der gleichen oder anderer erneut startbarer Funktionen. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Eine Anwendung sollte verwenden, z. B. **Wcsrlen** anstelle von **Wcslen** Wenn ein nachfolgender Aufruf von **Wcsrtombs** anstelle von **Wcstombs**.

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

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
