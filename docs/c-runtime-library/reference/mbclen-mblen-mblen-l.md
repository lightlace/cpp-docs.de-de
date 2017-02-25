---
title: "_mbclen, mblen, _mblen_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbclen"
  - "mblen"
  - "_mblen_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mblen"
  - "ftclen"
  - "_mbclen"
  - "tclen"
  - "_ftclen"
  - "_tclen"
  - "mbclen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbclen-Funktion"
  - "_mblen_l-Funktion"
  - "_tclen-Funktion"
  - "mbclen-Funktion"
  - "mblen-Funktion"
  - "mblen_l-Funktion"
  - "tclen-Funktion"
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _mbclen, mblen, _mblen_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Länge ab und bestimmt die Gültigkeit eines Multibytezeichens.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
size_t _mbclen(  
   const unsigned char *c   
);  
int mblen(  
   const char *mbstr,  
   size_t count   
);  
int _mblen_l(  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `c`  
 Multibytezeichen.  
  
 `mbstr`  
 Adresse einer Multibytezeichen\-Bytesequenz.  
  
 `count`  
 Anzahl zu überprüfender Bytes.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 `_mbclen` gibt 1 oder 2 zurück, je nachdem, ob das Multibytezeichen `c` 1 oder 2 Bytes lang ist.  Es gibt keine Fehlerrückgabe für `_mbclen`.  Wenn `mbstr` nicht `NULL` ist, gibt `mblen` die Länge des Multibytezeichens in Byte zurück.  Wenn `mbstr` gleich `NULL` ist oder auf das NULL\-Breitzeichen zeigt, gibt `mblen` 0 zurück.  Wenn das Objekt, auf das von `mbstr` gezeigt wird, kein gültiges Multibytezeichen innerhalb der ersten `count` Zeichen bildet, gibt `mblen` – 1 zurück.  
  
## Hinweise  
 Die `_mbclen`\-Funktion gibt die Länge des Multibytezeichens `c` in Byte zurück.  Wenn `c` nicht auf das führende Byte eines Multibytezeichens zeigt, wie durch einen impliziten Aufruf von `_ismbblead` bestimmt wird, ist das Ergebnis von `_mbclen` unvorhersehbar.  
  
 `mblen` gibt die Länge von `mbstr` in Byte zurück, wenn es sich um ein gültiges Multibytezeichen handelt und die Multibytezeichengültigkeit, die der Codepage zugeordnet ist, bestimmt wird.  `mblen` untersucht `count` oder weniger Byte, die in `mbstr` enthalten sind, jedoch nicht mehr als `MB_CUR_MAX` Byte.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tclen`|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|`_mbclen`|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbclen`|\<mbstring.h\>|  
|`mblen`|\<stdlib.h\>|  
|`_mblen_l`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_mblen.c  
/* illustrates the behavior of the mblen function  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    int      i;  
    char    *pmbc = (char *)malloc( sizeof( char ) );  
    wchar_t  wc   = L'a';  
  
    printf( "Convert wide character to multibyte character:\n" );  
    wctomb_s( &i, pmbc, sizeof(char), wc );  
    printf( "  Characters converted: %u\n", i );  
    printf( "  Multibyte character: %x\n\n", *pmbc );  
  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );  
  
    pmbc = NULL;  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );  
}  
```  
  
## Ausgabe  
  
```  
Convert wide character to multibyte character:  
  Characters converted: 1  
  Multibyte character: 61  
  
Length in bytes of multibyte character 61: 1  
Length in bytes of NULL multibyte character 0: 0  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbccpy, \_mbccpy\_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md)   
 [strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)