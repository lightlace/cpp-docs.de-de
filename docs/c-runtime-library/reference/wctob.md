---
title: "wctob | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wctob"
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
  - "wctob"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichen, Konvertieren"
  - "wctob-Funktion"
  - "Breitzeichen, Konvertieren"
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# wctob
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob ein Breitzeichen einem Mehrbytezeichen entspricht und seiner Mehrbytezeichendarstellung zurückgibt.  
  
## Syntax  
  
```  
int wctob(  
   wint_t wchar  
);  
```  
  
#### Parameter  
 `wchar`  
 So übersetzender Wert.  
  
## Rückgabewert  
 Wenn `wctob` erfolgreich ein Breitzeichen konvertiert, gibt es die Mehrbytezeichendarstellung, nur zurück, wenn das Mehrbytezeichen genau ein Byte lange dauern.  Wenn `wctob` ein Breitzeichen trifft, das er nicht auf einen Mehrbytezeichen konvertieren kann, oder das Mehrbytezeichen nicht genau ein Byte lange ist, gibt es a \- 1 zurück.  
  
## Hinweise  
 Die `wctob`\-Funktion konvertiert ein Breitzeichen, das in `wchar` zum entsprechenden Mehrbytezeichen enthalten ist, das vom Rückhol\- `int`\-Wert übergeben wird, wenn das Mehrbytezeichen genau ein Byte lange dauern.  
  
 Wenn `wctob` nicht erfolgreich war und kein entsprechendes Mehrbytezeichen gefunden wurde, wird die Funktion `errno` auf `EILSEQ` fest und gibt \-1 zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wctob`|\<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Programm veranschaulicht das Verhalten der Funktion `wcstombs`.  
  
```  
// crt_wctob.c  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    int     bChar = 0;  
    wint_t  wChar = 0;  
  
    // Set the corresponding wide character to exactly one byte.  
    wChar = (wint_t)'A';  
  
    bChar = wctob( wChar );  
    if (bChar == WEOF)  
    {  
        printf( "No corresponding multibyte character was found.\n");  
    }  
    else  
    {  
        printf( "Determined the corresponding multibyte character to"  
                " be \"%c\".\n", bChar);  
    }  
}  
  
```  
  
  **Bestimmte das entsprechende Mehrbytezeichen, um "A".**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)