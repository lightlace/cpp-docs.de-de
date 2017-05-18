---
title: mbrtowc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 481d67e2b2ccbc768b9afdbb4ede620dc237be43
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="mbrtowc"></a>mbrtowc
Konvertieren eines Multibytezeichens im aktuellen Gebietsschema in das entsprechende Breitzeichen mit der Möglichkeit des Neustarts in der Mitte eines Multibytezeichens.  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t mbrtowc(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count,  
   mbstate_t *mbstate  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wchar`  
 Adresse eines Breitzeichens für die Aufnahme der konvertierten Breitzeichenfolge (Typ `wchar_t`). Dieser Wert kann ein NULL-Zeiger sein, wenn keine Rückgabebreitzeichen erforderlich ist.  
  
 `mbchar`  
 Adresse einer Sequenz von Bytes (ein Multibytezeichen).  
  
 `count`  
 Anzahl zu überprüfender Bytes.  
  
 `mbstate`  
 Zeiger auf das Konvertierungzustandsobjekt. Wenn dieser Wert ein NULL-Zeiger ist, verwendet die Funktion ein statisches internes Konvertierungszustandsobjekt. Da das interne `mbstate_t`-Objekt nicht threadsicher ist, wird empfohlen, immer Ihr eigenes `mbstate`-Argument zu übergeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
 0  
 Die nächsten `count` oder weniger Bytes schließen das Multibytezeichen ab, das das NULLl-Breitzeichen darstellt, das in `wchar` gespeichert wird, wenn `wchar` kein NULL-Zeiger ist.  
  
 1 bis `count`, inklusive  
 Die nächsten `count` oder weniger Bytes schließen ein gültiges Multibytezeichen ab. Der zurückgegebene Wert ist die Anzahl der Bytes, die das Multybytezeichen abschließen. Das entsprechende Breitzeichen wird im `wchar` gespeichert, wenn `wchar` kein NULL-Zeiger ist.  
  
 (size_t)(-1)  
 Es ist ein Codierungsfehler aufgetreten. Die nächsten `count` oder weniger Bytes tragen nicht zu einem vollständigen und gültigen Multibytezeichen bei. In diesem Fall wird `errno` auf EILSEQ festgelegt, und der Konvertierungsumwandlungszustand in `mbstate` ist nicht angegeben.  
  
 (size_t)(-2)  
 Die nächsten `count` Bytes tragen zu einem unvollständigen, jedoch möglicherweisen gültigen Multibytezeichen bei und alle `count` Bytes wurden verarbeitet. Kein Wert wird in `wchar` gespeichert, aber `mbstate` wird so aktualisiert, dass die Funktion neu gestartet wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `mbchar` ist ein NULL-Zeiger ist, entspricht die Funktion dem Aufruf:  
  
 `mbrtowc(NULL, "", 1, &mbstate)`  
  
 In diesem Fall werden die Werte der Argumente `wchar` und `count` ignoriert.  
  
 Wenn `mbchar` kein NULL-Zeiger ist, überprüft die Funktion `count` Bytes aus`mbchar`, um die erforderliche Anzahl von Bytes bestimmen, die zum Abschließen des nächsten Multibytezeichens erforderlich sind. Wenn das nächste Zeichen gültig ist, wird das entsprechende Multibytezeichen in `wchar` gespeichert, wenn es kein NULL-Zeiger ist. Wenn es sich bei dem Zeichen um das entsprechende NULL-Breitzeichen handelt, ist der resultierenden Zustand von `mbstate` der ursprüngliche Konvertierungszustand.  
  
 Die `mbrtowc`-Funktion unterscheidet sich von [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md) durch die Neustartmöglichkeit. Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Eine Anwendung sollte beispielsweise `wcsrlen` anstelle von `wcslen` verwenden, wenn ein nachfolgender Aufruf von `wcsrtombs` anstelle von `wcstombs` verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Konvertiert ein Multibytezeichen in das entsprechende Breitzeichen.  
  
```  
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
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
Locale set to: "French_Canada.1252"  
Conversion succeeded!  
Multibyte String: AaBbCcÜïα∩≡xXyYzZ  
WC String: AaBbCcÜïα∩≡xXyYzZ  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`mbrtowc`|\<wchar.h>|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)
