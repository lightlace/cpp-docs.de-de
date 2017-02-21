---
title: "wcstombs, _wcstombs_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcstombs"
  - "_wcstombs_l"
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
  - "wcstombs"
  - "_wcstombs_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wcstombs_l-Funktion"
  - "Zeichen, Konvertieren"
  - "Zeichenfolgenkonvertierung, Mehrbytezeichenfolgen"
  - "Zeichenfolgenkonvertierung, Breitzeichen"
  - "wcstombs-Funktion"
  - "wcstombs_l-Funktion"
  - "Breitzeichen, Konvertieren"
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# wcstombs, _wcstombs_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Sequenz von Breitzeichen in der entsprechenden Reihenfolge von Mehrbytezeichen.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [wcstombs\_s, \_wcstombs\_s\_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md).  
  
## Syntax  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `mbstr`  
 Die Adresse einer Sequenz der Mehrbytezeichen.  
  
 `wcstr`  
 Die Adresse einer Sequenz der Breitzeichen.  
  
 `count`  
 Die maximale Anzahl von Bytes, die in der Mehrbyteausgabezeichenfolge gespeichert werden können.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Wenn `wcstombs` erfolgreich die Mehrbytezeichenfolge konvertiert, wird die Anzahl von Bytes zurück, die in die Mehrbyteausgabezeichenfolge, ausschließlich endendes `NULL` geschrieben werden \(falls vorhanden\).  Wenn das Argument `mbstr``NULL` ist, gibt `wcstombs` die erforderlichen Größe in Bytes der Zielzeichenfolge zurück.  Wenn `wcstombs` ein Breitzeichen trifft, das er nicht auf einen Mehrbytezeichen konvertieren kann, können Sie \- 1 umgewandelt, um zu `size_t` zurück und legt `errno` auf `EILSEQ` fest.  
  
## Hinweise  
 Die `wcstombs`\-Funktion konvertiert die Zeichenfolge mit Breitzeichen, die von `wcstr` in den entsprechenden Mehrbytezeichen gezeigt wird und speichert die Ergebnisse im `mbstr` \- Array.  Der `count`\-Parameter gibt die maximale Anzahl der Bytes an, die in der Mehrbyteausgabezeichenfolge \(das heißt, die Größe von `mbstr`\) gespeichert werden können.  Im Allgemeinen wird jedoch nicht, wie viele Bytes erforderlich sind, wenn Sie eine Zeichenfolge mit Breitzeichen konvertieren.  Einige Breitzeichen benötigen lediglich ein Byte in der Ausgabezeichenfolge; andere benötigen zwei.  Wenn zwei Bytes in der Mehrbyteausgabezeichenfolge für die einzelnen Breitzeichen in der Eingabezeichenfolge \(Breitzeichen\) einschließlich `NULL` gibt, ist das Ergebnis garantiert, um anzupassen.  
  
 Wenn `wcstombs` das NULL\-Breitzeichen \(L"\\0"\) entweder vor trifft oder, wenn `count` auftritt, wird es zu einem äußerst 0 konvertiert und anhält.  Daher ist die Mehrbytezeichenzeichenfolge bei `mbstr` auf NULL endende nur, wenn `wcstombs` ein NULL\-Breitzeichen während der Konvertierung gefunden wird.  Wenn die Sequenzen, die von `wcstr` und `mbstr` Überlappung, das Verhalten von `wcstombs` dargestellt werden, die definiert.  
  
 Wenn das Argument `mbstr``NULL` ist, gibt `wcstombs` die erforderlichen Größe in Bytes der Zielzeichenfolge zurück.  
  
 `wcstombs` überprüft die eigenen Parameter.  Wenn `wcstr``NULL` ist oder wenn `count` größer als `INT_MAX` ist, Aufrufe dieser Funktion Parameterhandler der ungültige, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, legt die Funktion `errno` auf `EINVAL` fest und gibt \-1 zurück.  
  
 `wcstombs` verwendet das aktuelle Gebietsschema jedes gebietsschemaabhängigen Verhalten; `_wcstombs_l` ist identisch, es verwendet das Gebietsschema, das ein\- stattdessen übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wcstombs`|\<stdlib.h\>|  
|`_wcstombs_l`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Programm veranschaulicht das Verhalten der Funktion `wcstombs`.  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
  **Bekehrtzeichenfolge mit breitzeichen:**  
 **Zeichen konvertiert: 13**  
 **Mehrbytezeichen: Hello, world.**   
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