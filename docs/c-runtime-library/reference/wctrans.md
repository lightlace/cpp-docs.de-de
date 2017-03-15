---
title: "wctrans | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wctrans"
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
  - "wctrans"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichencodes, wctrans"
  - "Zeichen, Codes"
  - "Zeichen, Konvertieren"
  - "wctrans-Funktion"
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# wctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt eine Zuordnung von einem Satz Zeichencodes zu anderen.  
  
## Syntax  
  
```  
wctrans_t wctrans(  
   const char *property   
);  
```  
  
#### Parameter  
 `property`  
 Eine Zeichenfolge, die einen der gültigen Transformationen angibt.  
  
## Rückgabewert  
 Wenn die Kategorie `LC_CTYPE` des aktuellen Gebietsschemas keine Zuordnung definiert, deren Name mit der Eigenschaftenzeichenfolge `property` übereinstimmt, Funktionsrückgaben null.  Andernfalls wird ein Wert ungleich 0 \(null\) zurück, der für die Verwendung als zweites Argument für einen nachfolgenden Aufruf für [towctrans](../../c-runtime-library/reference/towctrans.md) erstellen.  
  
## Hinweise  
 Diese Funktion bestimmt eine Zuordnung von einem Satz Zeichencodes zu anderen.  
  
 Die folgenden Paare von Aufrufen noch das gleiche Verhalten in allen Gebietsschemas, jedoch ist es möglich, weitere Zuordnungen sogar im "C " \- Gebietsschema zu definieren:  
  
|Funktion|Entspricht|  
|--------------|----------------|  
|`tolower(`  `c`  `)`|`towctrans(`  `c` `, wctrans("towlower" ) )`|  
|`towupper(`  `c`  `)`|`towctrans(`  `c` `, wctrans( "toupper" ) )`|  
  
## Anforderungen  
  
|Routine|Erforderliche Header|  
|-------------|--------------------------|  
|`wctrans`|\<wctype.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_wctrans.cpp  
// compile with: /EHsc  
// This example determines a mapping from one set of character  
// codes to another.   
  
#include <wchar.h>  
#include <wctype.h>  
#include <stdio.h>  
#include <iostream>  
  
int main()   
{  
    wint_t c = 'a';  
    printf_s("%d\n",c);  
  
    wctrans_t i = wctrans("toupper");  
    printf_s("%d\n",i);  
  
    wctrans_t ii = wctrans("towlower");  
    printf_s("%d\n",ii);  
  
    wchar_t wc = towctrans(c, i);  
    printf_s("%d\n",wc);  
}  
```  
  
  **97**  
**1**  
**0**  
**65**   
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)