---
title: "wcstombs_s, _wcstombs_s_l"
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
  - "_wcstombs_s_l"
  - "wcstombs_s"
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
  - "wcstombs_s"
  - "_wcstombs_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcstombs_s-Funktion"
  - "Zeichenfolgenkonvertierung, Breitzeichen"
  - "Konvertieren von Breitzeichen"
  - "_wcstombs_s_l-Funktion"
  - "wcstombs_s_l-Funktion"
  - "Zeichen, konvertieren"
  - "zeichenfolgenkonvertierung von Multibyte-Zeichenfolgen"
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 31
caps.handback.revision: "31"
ms.author: "corob"
manager: "ghogen"
---
# wcstombs_s, _wcstombs_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Sequenz von Zeichen in eine entsprechende Sequenz von Multibytezeichen. Eine Version von [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntax  
  
```  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count   
);  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `pReturnValue`  
 Die Anzahl von konvertierten Zeichen.  
  
 \[out\] `mbstr`  
 Die Adresse eines Puffers für den resultierenden konvertierten Zeichenfolge mit Multibytezeichen.  
  
 \[in\]`sizeInBytes`  
 Die Größe in Byte der `mbstr` Puffer.  
  
 \[in\] `wcstr`  
 Verweist auf die Breitzeichen\-Zeichenfolge konvertiert werden.  
  
 \[in\] `count`  
 Die maximale Anzahl von Bytes zum Speichern in der `mbstr` Puffer, nicht einschließlich des abschließenden Null\-Zeichens, oder [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[in\] `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
|Fehlerbedingung|Rückgabewert und `errno`|  
|---------------------|------------------------------|  
|`mbstr` ist `NULL` und `sizeInBytes` \> 0|`EINVAL`|  
|`wcstr` ist `NULL`|`EINVAL`|  
|Der Zielpuffer ist zu klein für die konvertierte Zeichenfolge enthalten \(es sei denn, `count` ist `_TRUNCATE`; finden Sie unter "Hinweise" weiter unten\)|`ERANGE`|  
  
 Wenn diese Bedingung eintritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md) . Wenn die Ausführung fortgesetzt werden kann, gibt die Funktion einen Fehlercode zurück und legt `errno` wie in der Tabelle angegeben fest.  
  
## Hinweise  
 Die `wcstombs_s` \-Funktion konvertiert eine Zeichenfolge mit Breitzeichen, die auf den `wcstr` in Zeichen im Puffer auf den gespeicherten `mbstr`. Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine der folgenden Bedingungen eintritt:  
  
-   Ein null\-Breitzeichen festgestellt wird  
  
-   Ein Breitzeichen, das konvertiert werden kann festgestellt wird  
  
-   Die Anzahl der Bytes in einem der `mbstr` Puffer ist gleich `count`.  
  
 Die Zielzeichenfolge ist immer Null\-terminiert \(selbst bei einem Fehler\).  
  
 Wenn `count` der spezielle Wert [\_TRUNCATE](../../c-runtime-library/truncate.md), dann `wcstombs_s` konvertiert, die Teil der Zeichenfolge wie in den Zielpuffer passt, wobei noch Platz für eine null\-Terminator bleibt.  
  
 Wenn `wcstombs_s` die Quellzeichenfolge erfolgreich konvertiert und speichert die Größe in Byte der konvertierten Zeichenfolge ist, einschließlich der null\-Terminator in `*``pReturnValue` \(bereitgestellte `pReturnValue` ist nicht `NULL`\). Dies tritt auf, auch wenn die `mbstr` Argument ist `NULL` und bietet eine Möglichkeit, die erforderliche Puffergröße bestimmen. Beachten Sie, dass bei `mbstr` ist `NULL`, `count` wird ignoriert.  
  
 Wenn `wcstombs_s` findet ein Breitzeichen, es kann nicht in einem multibyte\-Zeichen konvertiert, und speichert Sie 0 in `*``pReturnValue`, den Zielpuffer auf eine leere Zeichenfolge festgelegt wird, wird `errno` auf `EILSEQ`, und gibt `EILSEQ`.  
  
 Wenn die Sequenzen, auf die von `wcstr` und `mbstr` verwiesen wird, überlappen, ist das Verhalten von `wcstombs_s` nicht definiert.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, `wcstr` und `mbstr` nicht überlappen und dass `count` ordnungsgemäß reflektiert die Anzahl der Breitzeichen, konvertieren.  
  
 `wcstombs_s` verwendet das aktuelle Gebietsschema für jedes vom Gebietsschema abhängiges Verhalten. `_wcstombs_s_l` ist identisch mit `wcstombs` das übergebene Gebietsschema verwendet. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wcstombs_s`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Programm wird das Verhalten von der `wcstombs_s` Funktion.  
  
```  
// crt_wcstombs_s.c  
// This example converts a wide character  
// string to a multibyte character string.  
#include <stdio.h>  
#include <stdlib.h>  
#include <assert.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t   i;  
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t*pWCBuffer = L"Hello, world.";  
  
    printf( "Convert wide-character string:\n" );  
  
    // Conversion  
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,   
               pWCBuffer, (size_t)BUFFER_SIZE );  
  
    // Output  
    printf("   Characters converted: %u\n", i);  
    printf("    Multibyte character: %s\n\n",  
     pMBBuffer );  
  
    // Free multibyte character buffer  
    if (pMBBuffer)  
    {  
    free(pMBBuffer);  
    }  
}  
```  
  
```Output  
Konvertieren von Breitzeichen-Zeichenfolge: konvertiert Zeichen: 14 Multibytezeichen: Hello, World.  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)