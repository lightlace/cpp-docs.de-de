---
title: "mbrlen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "mbrlen"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbrlen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mbrlen-Funktion"
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# mbrlen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmen der Anzahl der Bytes, die zum Ausführen eines Multibytezeichens im aktuellen Gebietsschemas erforderlich sind, mit der Möglichkeit des Neustarts in der Mitte eines Multibytezeichens.  
  
## Syntax  
  
```  
size_t mbrlen(  
   const char * str,  
   size_t count,  
   mbstate_t * mbstate  
);  
```  
  
#### Parameter  
 `str`  
 Zeiger auf das nächste Byte, das in einer Multibytezeichenfolge überprüft werden soll.  
  
 `count`  
 Die maximale Anzahl der zu überprüfenden Bytes.  
  
 `mbstate`  
 Zeiger auf den aktuellen Umschaltzustand des ersten Bytes von `str`.  
  
## Rückgabewert  
 Einer der folgenden Werte:  
  
 0  
 Die nächsten `count` oder weniger Bytes schließen das Multibytezeichen ab, das Null\-Breitzeichen darstellt.  
  
 1 bis `count`, inklusive  
 Die nächsten `count` oder weniger Bytes schließen ein gültiges Multibytezeichen ab.  Der zurückgegebene Wert ist die Anzahl der Bytes, die das Multybytezeichen abschließen.  
  
 \(size\_t\)\(\-2\)  
 Die nächsten `count` Bytes tragen zu einem unvollständigen, jedoch möglicherweise gültigen Multibytezeichen bei und alle `count` Bytes wurden verarbeitet.  
  
 \(size\_t\)\(\-1\)  
 Es ist ein Codierungsfehler aufgetreten.  Die nächsten `count` oder weniger Bytes tragen nicht zu einem vollständigen und gültigen Multibytezeichen bei.  In diesem Fall wird `errno` auf EILSEQ festgelegt, und der Konvertierungszustand in `mbstate` ist nicht angegeben.  
  
## Hinweise  
 Die `mbrlen`\-Funktion prüft höchstens `count` Bytes, beginnend mit dem Byte, auf das von `str` gezeigt wird, um die Anzahl von Bytes zu bestimmen, die zum Abschließen des nächsten Multibytezeichens, einschließlich aller Umwandlungssequenzen, erforderlich sind.  Dies entspricht dem Aufruf von `mbrtowc(NULL, str, count, &mbstate)`, wobei `mbstate` entweder ein vom Benutzer bereitgestelltes `mbstate_t`\-Objekt oder ein statisches internes Objekt ist, das von der Bibliothek bereitgestellt wird.  
  
 Die `mbrlen`\-Funktion speichert und verwendet Umschaltzustand eines unvollständigen Multibytezeichens im `mbstate`\-Parameter.  Dadurch kann `mbrlen` bei Bedarf in der Mitte eines Multibytezeichens neu gestartet werden, wobei höchstens `count` Bytes untersucht werden.  Wenn `mbstate` ein NULL\-Zeiger ist, verwendet `mbrlen` ein internes, statisches `mbstate_t`\-Objekt zum Speichern des Umschaltzustands.  Da das interne `mbstate_t`\-Objekt nicht threadsicher ist, wird empfohlen, immer Ihren eigenen `mbstate`\-Parameter zuzuordnen und zu übergeben.  
  
 Die `mbrlen`\-Funktion unterscheidet sich von [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md) durch die Neustartmöglichkeit.  Der Umschaltzustand wird für nachfolgende Aufrufe der gleichen oder anderer Funktionen, die neu gestartet werden können, in `mbstate` gespeichert.  Wenn sowohl Funktionen, die neu gestartet werden können, als auch Funktionen, die nicht neu gestartet werden könnnen, verwendet werden, sind die Ergebnisse undefiniert.  Eine Anwendung sollte beispielsweise `wcsrlen` anstelle von `wcslen` verwenden, wenn ein nachfolgender Aufruf von `wcsrtombs` anstelle von `wcstombs.` verwendet wird.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|Nicht zutreffend|Nicht zutreffend|`mbrlen`|Nicht zutreffend|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`mbrlen`|\<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Dieses Beispiel zeigt, inwiefern die Interpretation von Multibytezeichen von der aktuellen Codepage abhängig ist, und demonstriert die Funktion zum Fortsetzen von `mbrlen`.  
  
```  
 // crt_mbrlen.c  
// Compile by using: cl crt_mbrlen.c  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
size_t Example(const char * pStr)  
{  
    size_t      charLen = 0;  
    size_t      charCount = 0;  
    mbstate_t   mbState = {0};  
  
    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&  
            charLen != (size_t)-1)  
    {  
        if (charLen != (size_t)-2) // if complete mbcs char,  
        {  
            charCount++;  
        }  
    }   
    return (charCount);  
}   
  
int main( void )  
{  
    int         cp;  
    size_t      charCount = 0;  
    const char  *pSample =   
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";  
  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
  
    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale  
    _setmbcp(932); // and Japanese multibyte code page  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
}  
```  
  
  **Codepage: 0**  
**é╨éτé¬é╚: Shift\-jis hiragana.  Zeichenanzahl: 29**  
**Codepage: 932**  
**????: Shift\-jis hiragana.  Zeichenanzahl: 25**    
## .NET Framework-Entsprechung  
 [System::String::Length](https://msdn.microsoft.com/en-us/library/system.string.length.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)