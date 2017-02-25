---
title: "mbstowcs, _mbstowcs_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "mbstowcs"
  - "_mbstowcs_l"
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
  - "mbstowcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbstowcs_l-Funktion"
  - "mbstowcs-Funktion"
  - "mbstowcs_l-Funktion"
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# mbstowcs, _mbstowcs_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Sequenz von Mehrbytezeichen zu der entsprechenden Reihenfolge von Breitzeichen.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [mbstowcs\_s, \_mbstowcs\_s\_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md).  
  
## Syntax  
  
```  
size_t mbstowcs(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count   
);  
size_t _mbstowcs_l(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t mbstowcs(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _mbstowcs_l(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `wcstr`  
 Die Adresse einer Sequenz der Breitzeichen.  
  
 \[in\] `mbstr`  
 Die Adresse einer Sequenz NULL beendete Mehrbytezeichen.  
  
 \[in\] `count`  
 Die maximale Anzahl der Mehrbytezeichen zu konvertieren.  
  
 \[in\] `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Wenn `mbstowcs` erfolgreich die Quellzeichenfolge konvertiert, wird die Anzahl der konvertierten Mehrbytezeichen zurück.  Wenn das Argument `wcstr``NULL` ist, gibt die Funktion der erforderlichen Größe \(Breitzeichen\) in der Zielzeichenfolge zurück.  Wenn `mbstowcs` ein ungültiges Mehrbytezeichen stößt, gibt es \- 1 zurück.  Falls der Rückgabewert `count` ist, ist die Zeichenfolge mit Breitzeichen nicht auf NULL enden.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `wcstr` und `mbstr` nicht überschneiden und dass `count` richtig die Anzahl Mehrbytezeichen an verschiedenen mitgeteilt.  
  
## Hinweise  
 Die `mbstowcs`\-Funktion konvertiert bis zu einer maximalen Anzahl `count` Mehrbytezeichen, die von `mbstr` in eine Zeichenfolge aus entsprechenden Breitzeichen dargestellt werden, die durch das aktuelle Gebietsschema bestimmt werden.  Sie speichert die resultierende Zeichenfolge mit Breitzeichen an der Adresse, die durch `wcstr` dargestellt wird *.* Das Ergebnis ist auf eine Reihe von Aufrufen zu `mbtowc` ähnlich.  Wenn `mbstowcs` das Einzelbytenull\-zeichen \("\\0"\) entweder vor trifft oder, wenn `count` auftritt, das Nullzeichen zu einem NULL\-Breitzeichen wird \(L"\\0"\) und wird beendet.  Daher ist die Zeichenfolge mit Breitzeichen bei `wcstr` auf NULL endende nur, wenn ein NULL\-Zeichen während der Konvertierung gefunden wird.  Wenn die Sequenzen, die von `wcstr` und `mbstr` Überlappung, das Verhalten dargestellt werden, die definiert.  
  
 Wenn das Argument `wcstr``NULL` ist, gibt `mbstowcs` die Anzahl der Breitzeichen, die sich aus der Konvertierung zu erhalten, ohne ein abschließendes zurück.  Die Quellzeichenfolge muss auf null endende sein, sodass der richtige Wert zurückgegeben werden kann.  Wenn Sie die resultierende Zeichenfolge mit Breitzeichen auf null endende sein müssen, fügen Sie dem zurückgegebenen Wert hinzu.  
  
 Wenn `mbstr` das Argument `NULL` ist oder wenn `count``INT_MAX` ist \>, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird errno auf `EINVAL` und Funktionsrückgaben \-1 festgelegt.  
  
 `mbstowcs` verwendet das aktuelle Gebietsschema jedes gebietsschemaabhängigen Verhalten; `_mbstowcs_l`  ist identisch, es verwendet das Gebietsschema, das ein\- stattdessen übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`mbstowcs`|\<stdlib.h\>|  
|`_mbstowcs_l`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_mbstowcs.c  
// compile with: /W3  
// illustrates the behavior of the mbstowcs function  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main( void )  
{  
    size_t size;  
    int nChar = 2; // number of characters to convert  
    int requiredSize;  
  
    unsigned char    *pmbnull  = NULL;  
    unsigned char    *pmbhello = NULL;  
    char* localeInfo;  
  
    wchar_t *pwchello = L"\x3042\x3043"; // 2 Hiragana characters  
    wchar_t *pwc;  
  
    /* Enable the Japanese locale and codepage */  
    localeInfo = setlocale(LC_ALL, "Japanese_Japan.932");  
    printf("Locale information set to %s\n", localeInfo);  
  
    printf( "Convert to multibyte string:\n" );  
  
    requiredSize = wcstombs( NULL, pwchello, 0); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    printf("  Required Size: %d\n", requiredSize);  
  
    /* Add one to leave room for the null terminator. */  
    pmbhello = (unsigned char *)malloc( requiredSize + 1);  
    if (! pmbhello)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = wcstombs( pmbhello, pwchello, requiredSize + 1); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    if (size == (size_t) (-1))  
    {  
        printf("Couldn't convert string. Code page 932 may"  
                " not be available.\n");  
        return 1;  
    }  
    printf( "  Number of bytes written to multibyte string: %u\n",  
            (unsigned int) size );  
    printf( "  Hex values of the " );  
    printf( " multibyte characters: %#.2x %#.2x %#.2x %#.2x\n",  
            pmbhello[0], pmbhello[1], pmbhello[2], pmbhello[3] );  
    printf( "  Codepage 932 uses 0x81 to 0x9f as lead bytes.\n\n");  
  
    printf( "Convert back to wide-character string:\n" );  
  
    /* Assume we don't know the length of the multibyte string.  
     Get the required size in characters, and allocate enough space. */  
  
    requiredSize = mbstowcs(NULL, pmbhello, 0); // C4996  
    /* Add one to leave room for the NULL terminator */  
    pwc = (wchar_t *)malloc( (requiredSize + 1) * sizeof( wchar_t ));  
    if (! pwc)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = mbstowcs( pwc, pmbhello, requiredSize + 1); // C4996  
    if (size == (size_t) (-1))  
    {  
       printf("Couldn't convert string--invalid multibyte character.\n");  
    }  
    printf( "  Characters converted: %u\n", (unsigned int)size );  
    printf( "  Hex value of first 2" );  
    printf( " wide characters: %#.4x %#.4x\n\n", pwc[0], pwc[1] );  
    free(pwc);  
    free(pmbhello);  
}  
```  
  
  **Gebietsschemainformationen festgelegt auf Japanese\_Japan.932**  
**in ein Mehrbytezeichenfolge:**  
 **Erforderliche Größe: 4**  
 **Anzahl Bytes geschrieben zur Mehrbytezeichenfolge: 4**  
 **Hexadezimalwerte der Mehrbytezeichen: 0x82 0xa0 0x82 0xa1**  
 **Verwendung von der Codepage 932 und 0x9f als führende Bytes.**  
**konvertieren wieder Zeichenfolge mit Breitzeichen:**  
 **Zeichen konvertiert: 2**  
 **Hexadezimalwert von Breitzeichen ersten 2: 0x3042 0x3043**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)