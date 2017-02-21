---
title: "wctomb_s, _wctomb_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wctomb_s_l"
  - "wctomb_s"
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
  - "wctomb_s"
  - "_wctomb_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctomb_s_l-Funktion"
  - "Zeichen, Konvertieren"
  - "Zeichenfolgenkonvertierung, Mehrbytezeichenfolgen"
  - "Zeichenfolgenkonvertierung, Breitzeichen"
  - "wctomb_s-Funktion"
  - "wctomb_s_l-Funktion"
  - "Breitzeichen, Konvertieren"
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# wctomb_s, _wctomb_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert ein Breitzeichen zum entsprechenden Mehrbytezeichen.  Eine Version von [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 \[out\] `pRetValue`  
 Die Anzahl der Bytes oder ein Code, der das Ergebnis angibt.  
  
 \[out\] `mbchar`  
 Die Adresse eines Mehrbytezeichens.  
  
 \[in\] `sizeInBytes`  
 Größe des Puffers `mbchar`.  
  
 \[in\] `wchar`  
 Bei einem Breitzeichen.  
  
 \[in\] `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
 Fehlerbedingungen  
  
|`mbchar`|`sizeInBytes`|Rückgabewert|`pRetValue`|  
|--------------|-------------------|------------------|-----------------|  
|`NULL`|\>0|`EINVAL`|nicht geändert|  
|any|\>`INT_MAX`|`EINVAL`|nicht geändert|  
|any|zu klein|`EINVAL`|nicht geändert|  
  
 Wenn eine der oben genannten Fehlerzustände, tritt der ungültige Parameterhandler wird aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt `wctomb``EINVAL` zurück und setzt `errno` auf `EINVAL`.  
  
## Hinweise  
 Die `wctomb_s`\-Funktion konvertiert sein `wchar`\-Argument zum entsprechenden Mehrbytezeichen und speichert das Ergebnis bei `mbchar`.  Sie können die Funktion von einem beliebigen Punkt in jedes Programm aufrufen.  
  
 Wenn `wctomb_s` das Breitzeichen einem Mehrbytezeichen konvertiert, werden die Anzahl von Bytes \(die nie größer als `MB_CUR_MAX` ist, in das Breitzeichen in die ganze Zahl ein, die auf den durch `pRetValue` gezeigt wird.  Wenn `wchar` das NULL\-Breitzeichen \(L"\\0"\) ist, wird `wctomb_s``pRetValue` mit 1. aus.  Wenn der Zielzeiger `mbchar` NULL ist, gibt `wctomb_s` 0 in `pRetValue` ein.  Wenn die Konvertierung nicht im aktuellen Gebietsschema möglich ist, wird `wctomb_s` \- 1 in `pRetValue`.  
  
 `wctomb_s` verwendet das aktuelle Gebietsschema zu gebietsschemaabhängiger Informationen; `_wctomb_s_l` ist identisch, es verwendet das Gebietsschema, das ein\- stattdessen übergeben wird.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wctomb_s`|\<stdlib.h\>|  
|`_wctomb_s_l`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Programm veranschaulicht das Verhalten der Funktion `wctomb`.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
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