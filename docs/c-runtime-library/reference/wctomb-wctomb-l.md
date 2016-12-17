---
title: "wctomb, _wctomb_l"
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
  - "_wctomb_l"
  - "wctomb"
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
  - "wctomb"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wctomb_l-Funktion"
  - "Zeichen, Konvertieren"
  - "Zeichenfolgenkonvertierung, Mehrbytezeichenfolgen"
  - "Zeichenfolgenkonvertierung, Breitzeichen"
  - "wctomb-Funktion"
  - "wctomb_l-Funktion"
  - "Breitzeichen, Konvertieren"
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
caps.latest.revision: 23
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# wctomb, _wctomb_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert ein Breitzeichen zum entsprechenden Mehrbytezeichen.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md).  
  
## Syntax  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `mbchar`  
 Die Adresse eines Mehrbytezeichens.  
  
 `wchar`  
 Bei einem Breitzeichen.  
  
## Rückgabewert  
 Wenn `wctomb` das Breitzeichen einem Mehrbytezeichen konvertiert, wird die Anzahl von Bytes \(die nie größer als `MB_CUR_MAX` ist\), im Breitzeichen zurück.  Wenn `wchar` das NULL\-Breitzeichen \(L"\\0"\) ist, `wctomb` gibt 1 zurück.  Wenn der Zielzeiger `mbchar` NULL ist, `wctomb` gibt 0 zurück.  Wenn die Konvertierung nicht im aktuellen Gebietsschema möglich ist, wird `wctomb` zurückgegeben \- 1 und `errno` ist auf `EILSEQ` festgelegt.  
  
## Hinweise  
 Die `wctomb`\-Funktion konvertiert sein `wchar`\-Argument zum entsprechenden Mehrbytezeichen und speichert das Ergebnis bei `mbchar`.  Sie können die Funktion von einem beliebigen Punkt in jedes Programm aufrufen.  `wctomb` verwendet das aktuelle Gebietsschema jedes gebietsschemaabhängigen Verhalten; `_wctomb_l` ist mit `wctomb` identisch, es verwendet das Gebietsschema, das ein\- stattdessen übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 `wctomb` überprüft die eigenen Parameter.  Wenn `mbchar` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno` auf `EINVAL` und Funktionsrückgaben \-1 festgelegt.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wctomb`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Programm veranschaulicht das Verhalten der wctomb Funktion.  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
  **Konvertiert ein Breitzeichen:**  
 **Zeichen konvertiert: 1**  
 **Mehrbytezeichen: a**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)