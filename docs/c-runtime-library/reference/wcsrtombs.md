---
title: "wcsrtombs"
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
  - "wcsrtombs"
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
  - "wcsrtombs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcsrtombs-Funktion"
  - "Zeichenfolgenkonvertierung, Breitzeichen"
  - "Breitzeichen, Zeichenfolgen"
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: 26
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# wcsrtombs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge mit Breitzeichen zu seiner Mehrbytezeichenzeichenfolgendarstellung.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [wcsrtombs\_s](../../c-runtime-library/reference/wcsrtombs-s.md).  
  
## Syntax  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `mbstr`  
 Der Adressenplatz der resultierenden konvertierten Mehrbytezeichenzeichenfolge.  
  
 \[in\] `wcstr`  
 Zeigt indirekt auf den Speicherort der zu konvertierende Zeichenfolge mit Breitzeichen.  
  
 \[in\] `count`  
 Die Anzahl für zu konvertierenden Zeichens.  
  
 \[in\] `mbstate`  
 Ein Zeiger auf ein `mbstate_t` Konvertierungszustandsobjekt.  
  
## Rückgabewert  
 Gibt die Anzahl an Bytes konvertiert nicht erfolgreich, einschließlich das ungültige endgültige NULL\-Zeichen\-Byte \(falls vorhanden\); andernfalls \-1 zurück, wenn ein Fehler aufgetreten ist.  
  
## Hinweise  
 Die `wcsrtombs`\-Funktion konvertiert eine Zeichenfolge mit Breitzeichen und beginnt im angegebenen Konvertierungszustand, der in `mbstate`, im indirekten spitzen die Werte zu in `wcstr`, in die Adresse von `mbstr` enthalten ist.  Die Konvertierung wird für jedes Zeichen bis fort: nachdem eine NULL\-Zeichenfolge, die beendet Breitzeichen, aufgetreten ist, wenn ein nicht übereinstimmendes Zeichen festgestellt wird, oder das nächste Zeichen als der Grenzwert übersteigt, die in `count` enthalten war.  Wenn `wcsrtombs` das NULL\-Breitzeichen \(L"\\0"\) entweder vor trifft oder, wenn `count` auftritt, wird es zu einem äußerst 0 konvertiert und anhält.  
  
 Daher ist die Mehrbytezeichenzeichenfolge bei `mbstr` auf NULL endende nur, wenn `wcsrtombs` ein Breitzeichennull\-zeichen während der Konvertierung gefunden wird.  Wenn die Sequenzen, die von `wcstr` und `mbstr` Überlappung, das Verhalten von `wcsrtombs` dargestellt werden, die definiert.  `wcsrtombs` wird durch die LC\_TYPE\-Kategorie des aktuellen Gebietsschemas beeinflusst.  
  
 Die `wcsrtombs`\-Funktion unterscheidet sich von [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) durch ihre Neustartfähigkeit.  Der Konvertierungszustand wird in `mbstate` für nachfolgende Aufrufe an den gleichen oder anderen restartable Funktionen gespeichert.  Ergebnisse werden undefiniert, wenn Sie die Verwendung von restartable und nonrestartable Funktionen kombiniert.  Beispielsweise würde eine Anwendung `wcsrlen` statt `wcsnlen` verwenden, wenn ein nachfolgender Aufruf `wcsrtombs` statt `wcstombs` verwendet wurden.  
  
 Wenn das Argument `mbstr``NULL` ist, gibt `wcsrtombs` die erforderlichen Größe in Bytes der Zielzeichenfolge zurück.  Wenn `mbstate` NULL ist, wird der interne `mbstate_t` Konvertierungszustand verwendet.  Wenn die Zeichensequenz `wchar` keine entsprechende Mehrbytezeichendarstellung hat, wird \-1 zurückgegeben und `errno` ist auf `EILSEQ` festgelegt.  
  
 In C\+\+ ist diese Funktion eine Vorlagenüberladung, die aufgerufen wird, das später, speichern Entsprechung dieser Funktion.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Ausnahmen  
 Die Funktion `wcsrtombs` ist multithreadsicher, solange keine Funktion im aktuellen Thread `setlocale` aufruft, wenn diese Funktion ausführt und `mbstate` nicht NULL ist.  
  
## Beispiel  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
  **Die Zeichenfolge wurde erfolgreich konvertiert.**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`wcsrtombs`|\<wchar.h\>|  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)