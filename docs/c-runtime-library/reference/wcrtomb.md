---
title: "wcrtomb | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcrtomb"
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
  - "wcrtomb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichen, Konvertieren"
  - "Mehrbytezeichen"
  - "wcrtomb-Funktion"
  - "Breitzeichen, Konvertieren"
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# wcrtomb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert ein Breitzeichen in seine Mehrbytezeichendarstellung.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md).  
  
## Syntax  
  
```  
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
  
#### Parameter  
 \[out\] `mbchar`  
 Das resultierendes die Mehrbyte\-Codepage konvertierte Zeichen.  
  
 \[in\] `wchar`  
 Bei einem Breitzeichen zu konvertieren.  
  
 \[in\] `mbstate`  
 Ein Zeiger auf ein `mbstate_t`\-Objekt.  
  
## Rückgabewert  
 Gibt die Anzahl von Bytes erforderlich, um das konvertierte Mehrbytezeichen; andernfalls \-1 darstellen zurück, wenn ein Fehler auftritt.  
  
## Hinweise  
 Die `wcrtomb`\-Funktion konvertiert ein Breitzeichen und beginnt im angegebenen Konvertierungszustand, der in `mbstate`, den Wert enthalten ist, der in `wchar`, in die Adresse enthalten wird, die durch `mbchar` dargestellt wird.  Der Rückgabewert ist die Anzahl von Bytes erforderlich, um das entsprechende Mehrbytezeichen darzustellen, aber es wird nicht mehr als `MB_CUR_MAX` Bytes zurück.  
  
 Wenn `mbstate` NULL ist, wird das interne `mbstate_t`\-Objekt, das den Konvertierungszustand von `mbchar` enthält, verwendet.  Wenn die Zeichensequenz `wchar` keine entsprechende Mehrbytezeichendarstellung hat, wird \-1 zurückgegeben und `errno` ist auf `EILSEQ` festgelegt.  
  
 Die `wcrtomb`\-Funktion unterscheidet sich von [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) durch ihre Neustartfähigkeit.  Der Konvertierungszustand wird in `mbstate` für nachfolgende Aufrufe an den gleichen oder anderen restartable Funktionen gespeichert.  Ergebnisse werden undefiniert, wenn Sie die Verwendung von restartable und nonrestartable Funktionen kombiniert.  Beispielsweise würde eine Anwendung `wcsrlen` statt `wcsnlen` verwenden, wenn ein nachfolgender Aufruf `wcsrtombs` statt `wcstombs` verwendet wurden.  
  
 In C\+\+ ist diese Funktion eine Vorlagenüberladung, die aufgerufen wird, das später speichern, Entsprechungen dieser Funktion.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Ausnahmen  
 Die Funktion `wcrtomb` ist multithreadsicher, solange keine Funktion im aktuellen Thread `setlocale` aufruft, wenn diese Funktion ausführt und während `mbstate` NULL ist.  
  
## Beispiel  
  
```  
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
  
  **Das entsprechende Breitzeichen "Q" wurde in "Q\-" Mehrbytezeichen konvertiert.**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wcrtomb`|\<wchar.h\>|  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)