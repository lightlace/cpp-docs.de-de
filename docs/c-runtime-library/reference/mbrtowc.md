---
title: "mbrtowc"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "mbrtowc"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbrtowc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "mbrtowc-Funktion"
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# mbrtowc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertieren eines Multibytezeichens im aktuellen Gebietsschema in das entsprechende Breitzeichen mit der Möglichkeit des Neustarts in der Mitte eines Multibytezeichens.  
  
## Syntax  
  
```  
size_t mbrtowc(  
   wchar_t *wchar,  
   const char *mbchar,  
   size_t count,  
   mbstate_t *mbstate  
);  
```  
  
#### Parameter  
 `wchar`  
 Adresse eines Breitzeichens für die Aufnahme der konvertierten Breitzeichenfolge \(Typ `wchar_t`\).  Dieser Wert kann ein NULL\-Zeiger sein, wenn keine Rückgabebreitzeichen erforderlich ist.  
  
 `mbchar`  
 Adresse einer Sequenz von Bytes \(ein Multibytezeichen\).  
  
 `count`  
 Anzahl zu überprüfender Bytes.  
  
 `mbstate`  
 Zeiger auf das Konvertierungzustandsobjekt.  Wenn dieser Wert ein NULL\-Zeiger ist, verwendet die Funktion ein statisches internes Konvertierungszustandsobjekt.  Da das interne `mbstate_t`\-Objekt nicht threadsicher ist, wird empfohlen, immer Ihr eigenes `mbstate`\-Argument zu übergeben.  
  
## Rückgabewert  
 Einer der folgenden Werte:  
  
 0  
 Die nächsten `count` oder weniger Bytes schließen das Multibytezeichen ab, das das NULLl\-Breitzeichen darstellt, das in `wchar` gespeichert wird, wenn `wchar` kein NULL\-Zeiger ist.  
  
 1 bis `count`, inklusive  
 Die nächsten `count` oder weniger Bytes schließen ein gültiges Multibytezeichen ab.  Der zurückgegebene Wert ist die Anzahl der Bytes, die das Multybytezeichen abschließen.  Das entsprechende Breitzeichen wird im `wchar` gespeichert, wenn `wchar` kein NULL\-Zeiger ist.  
  
 \(size\_t\)\(\-1\)  
 Es ist ein Codierungsfehler aufgetreten.  Die nächsten `count` oder weniger Bytes tragen nicht zu einem vollständigen und gültigen Multibytezeichen bei.  In diesem Fall wird `errno` auf EILSEQ festgelegt, und der Konvertierungsumwandlungszustand in `mbstate` ist nicht angegeben.  
  
 \(size\_t\)\(\-2\)  
 Die nächsten `count` Bytes tragen zu einem unvollständigen, jedoch möglicherweisen gültigen Multibytezeichen bei und alle `count` Bytes wurden verarbeitet.  Kein Wert wird in `wchar` gespeichert, aber `mbstate` wird so aktualisiert, dass die Funktion neu gestartet wird.  
  
## Hinweise  
 Wenn `mbchar` ist ein NULL\-Zeiger ist, entspricht die Funktion dem Aufruf:  
  
 `mbrtowc(NULL, "", 1, &mbstate)`  
  
 In diesem Fall werden die Werte der Argumente `wchar` und `count` ignoriert.  
  
 Wenn `mbchar` kein NULL\-Zeiger ist, überprüft die Funktion `count` Bytes aus`mbchar`, um die erforderliche Anzahl von Bytes bestimmen, die zum Abschließen des nächsten Multibytezeichens erforderlich sind.  Wenn das nächste Zeichen gültig ist, wird das entsprechende Multibytezeichen in `wchar` gespeichert, wenn es kein NULL\-Zeiger ist.  Wenn es sich bei dem Zeichen um das entsprechende NULL\-Breitzeichen handelt, ist der resultierenden Zustand von `mbstate` der ursprüngliche Konvertierungszustand.  
  
 Die `mbrtowc`\-Funktion unterscheidet sich von [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md) durch die Neustartmöglichkeit.  Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert.  Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Eine Anwendung sollte beispielsweise `wcsrlen` anstelle von `wcslen` verwenden, wenn ein nachfolgender Aufruf von `wcsrtombs` anstelle von `wcstombs` verwendet wird.  
  
## Beispiel  
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
  
## Beispielausgabe  
  
```  
Locale set to: "French_Canada.1252"  
Conversion succeeded!  
Multibyte String: AaBbCcÜïα∩≡xXyYzZ  
WC String: AaBbCcÜïα∩≡xXyYzZ  
```  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`mbrtowc`|\<wchar.h\>|  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)