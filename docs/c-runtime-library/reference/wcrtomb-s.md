---
title: "wcrtomb_s"
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
  - "wcrtomb_s"
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
  - "wcrtomb_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Konvertieren von Breitzeichen"
  - "wcrtomb_s-Funktion"
  - "Mehrbytezeichen"
  - "Zeichen, konvertieren"
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# wcrtomb_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Breitzeichen in seine Darstellung für multibyte\-Zeichenfolgen zu konvertieren. Eine Version von [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntax  
  
```  
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
  
#### Parameter  
 \[out\] `pReturnValue`  
 Gibt die Anzahl der geschriebenen Bytes oder\-1 zurück, wenn ein Fehler aufgetreten.  
  
 \[out\] `mbchar`  
 Die resultierende Multibyte konvertiert Zeichen.  
  
 \[in\] `sizeOfmbchar`  
 Die Größe der `mbchar` Variablen in Bytes.  
  
 \[in\] `wchar`  
 Ein zu konvertierendes Breitzeichen.  
  
 \[in\] `mbstate`  
 Ein Zeiger auf ein `mbstate_t`\-Objekt.  
  
## Rückgabewert  
 Gibt 0 \(null\) oder ein `errno` \-Wert, wenn ein Fehler auftritt.  
  
## Hinweise  
 Die `wcrtomb_s` \-Funktion konvertiert ein Breitzeichen, ab der angegebenen konvertierungszustand in enthaltenen `mbstate`, von dem Wert in `wchar`, in die Adresse, die als `mbchar`. Die `pReturnValue` Wert wird die Anzahl von Bytes konvertiert, jedoch nicht mehr als `MB_CUR_MAX` Bytes oder 1, wenn ein Fehler aufgetreten.  
  
 Wenn `mbstate` null ist, den internen `mbstate_t` Konvertierung Status verwendet. Wenn das Zeichen in enthalten `wchar` verfügt nicht über ein entsprechendes Multibytezeichen, den Wert der `pReturnValue` beträgt\-1, und die Funktion zurück der `errno` Wert `EILSEQ`.  
  
 Die `wcrtomb_s` \-Funktion unterscheidet sich von [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) durch die Sicherung. Der Konvertierungszustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert. Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert. Eine Anwendung verwendet z. B. `wcsrlen` statt `wcslen`, wenn ein nachfolgender Aufruf von `wcsrtombs_s` anstelle von verwendet wurden `wcstombs_s.`  
  
 In C\+\+ wird die Verwendung dieser Funktion durch vorlagenüberladungen vereinfacht; die Überladungen können Pufferlänge automatisch \(Dadurch entfällt die Notwendigkeit einer größenargument angeben\), und sie können automatisch die ältere, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Ausnahmen  
 Die `wcrtomb_s` \-Funktion ist multithreadsicher ist, solange keine Funktion im aktuellen Thread ruft `setlocale` während der Ausführung dieser Funktion und der `mbstate` ist null.  
  
## Beispiel  
  
```  
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
Wurde das entsprechende Breitzeichen "Q" konvertiert eine das Multibytezeichen "Q".  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wcrtomb_s`|\<wchar.h\>|  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)