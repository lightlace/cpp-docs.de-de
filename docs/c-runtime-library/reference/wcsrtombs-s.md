---
title: "wcsrtombs_s"
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
  - "wcsrtombs_s"
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
  - "wcsrtombs_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Zeichenfolgenkonvertierung, Breitzeichen"
  - "wcsrtombs_s-Funktion"
  - "Breitzeichen, Zeichenfolgen"
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: 27
caps.handback.revision: "25"
ms.author: "corob"
manager: "ghogen"
---
# wcsrtombs_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge mit Breitzeichen zu seiner Mehrbytezeichenzeichenfolgendarstellung.  Eine Version von [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `pReturnValue`  
 Die Anzahl der Zeichen konvertiert.  
  
 \[out\] `mbstr`  
 Die Adresse eines Puffers für Zurückhalten konvertierte Mehrbytezeichenzeichenfolge.  
  
 \[out\] `sizeInBytes`  
 Die Größe in Bytes des Puffers `mbstr`.  
  
 \[in\] `wcstr`  
 Punkte die zu konvertierende Zeichenfolge mit Breitzeichen.  
  
 \[in\] `count`  
 Die maximale Anzahl der im Puffer `mbstr` gespeichert werden, Bytes oder [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[in\] `mbstate`  
 Ein Zeiger auf ein `mbstate_t` Konvertierungszustandsobjekt.  
  
## Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
|Fehlerstatus|Rückgabewert und `errno`|  
|------------------|------------------------------|  
|`mbstr` ist `NULL` und `sizeInBytes` \> 0|`EINVAL`|  
|`wcstr` ist `NULL`|`EINVAL`|  
|Der Zielpuffer ist zu klein, die konvertierte Zeichenfolge zu enthalten \(es sei denn, `count` ; `_TRUNCATE` ist siehe Hinweise\) unten|`ERANGE`|  
  
 Wenn diese Bedingungen auftritt, wird die ungültige Parameterausnahme aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, gibt die Funktion einen Fehlercode zurück und legt `errno` fest, wie in der Tabelle angegeben.  
  
## Hinweise  
 Die `wcsrtombs_s`\-Funktion konvertiert eine Zeichenfolge mit Breitzeichen, die von `wcstr` in die Mehrbytezeichen dargestellt werden, die im Puffer gespeichert werden, auf den `mbstr`, mit dem Konvertierungszustandes gezeigt wird, die in `mbstate` enthalten ist.  Die Konvertierung wird für jedes Zeichen fortgesetzt, bis eine dieser Bedingungen erfüllt ist:  
  
-   Ein NULL\-Makro Breitzeichen auftritt  
  
-   Bei einem Breitzeichen, die nicht konvertiert werden kann, wird ausgeführt  
  
-   Die Anzahl der Bytes, die im `mbstr` Puffer gespeichert werden, entspricht `count`.  
  
 Die Zielzeichenfolge ist immer auf NULL enden \(selbst im Falle eines Fehlers.\)  
  
 Wenn `count` den speziellen Wert [\_TRUNCATE](../../c-runtime-library/truncate.md) ist, konvertiert `wcsrtombs_s` so weit der Zeichenfolge, wie in den Zielpuffer passt, wobei Platz für einen Nullterminator weiterhin beibehalten.  
  
 Wenn `wcsrtombs_s` erfolgreich die Quellzeichenfolge konvertiert, wird die Größe in Bytes der konvertierten Zeichenfolge, einschließlich das NULL\-Zeichen, in `*`\(ein `pReturnValue` bereit gestelltes `pReturnValue` nicht `NULL` ist\).  Dies tritt auf, `mbstr`, wenn das Argument `NULL` und bietet eine Möglichkeit, die erforderliche Puffergröße zu ermitteln.  Beachten Sie, dass, wenn `mbstr``NULL` ist, die `count` ignoriert wird.  
  
 Wenn `wcsrtombs_s` ein Breitzeichen trifft, das er nicht auf einen Mehrbytezeichen konvertieren kann, wird \-1 in `*``pReturnValue`, legt den Zielpuffer auf eine leere Zeichenfolge fest, wird `errno` auf `EILSEQ` festgelegt und `EILSEQ` zurückgegeben.  
  
 Wenn die Sequenzen, die von `wcstr` und `mbstr` Überlappung, das Verhalten von `wcsrtombs_s` dargestellt werden, die definiert.  `wcsrtombs_s` wird durch die LC\_TYPE\-Kategorie des aktuellen Gebietsschemas beeinflusst.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `wcstr` und `mbstr` nicht überschneiden und dass `count` richtig die Anzahl der Breitzeichen an verschiedenen mitgeteilt.  
  
 Die `wcsrtombs_s`\-Funktion unterscheidet sich von [wcstombs\_s, \_wcstombs\_s\_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md) durch ihre Neustartfähigkeit.  Der Konvertierungszustand wird in `mbstate` für nachfolgende Aufrufe an den gleichen oder anderen restartable Funktionen gespeichert.  Ergebnisse werden undefiniert, wenn Sie die Verwendung von restartable und nonrestartable Funktionen kombiniert.  Beispielsweise würde eine Anwendung `wcsrlen` statt `wcslen` verwenden, wenn ein nachfolgender Aufruf `wcsrtombs_s` statt `wcstombs_s.` verwendet wurden  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Ausnahmen  
 Die Funktion `wcsrtombs_s` ist multithreadsicher, solange keine Funktion im aktuellen Thread `setlocale` aufruft, wenn diese Funktion ausführt und `mbstate` NULL ist.  
  
## Beispiel  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
  **Die Zeichenfolge wurde erfolgreich konvertiert.**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wcsrtombs_s`|\<wchar.h\>|  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)