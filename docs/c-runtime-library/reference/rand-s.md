---
title: "rand_s"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "rand_s"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "rand_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Kryptografisch sichere Zufallszahlen"
  - "Generieren von pseudozufälligen Zahlen"
  - "Zahlen, Generieren von pseudozufälligen"
  - "Zahlen, Pseudozufällig"
  - "Pseudozufallszahlen"
  - "rand_s-Funktion"
  - "Zufallszahlen, Kryptografisch sicher"
  - "Zufallszahlen, Generieren"
ms.assetid: d6a0be60-997d-4904-8411-8aea6839cc94
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# rand_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generiert eine Pseudozufallszahl.  Eine Version von [rand](../../c-runtime-library/reference/rand.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t rand_s(   unsigned int* randomValue);  
```  
  
## Rückgabewert  
 Null wenn erfolgreich andernfalls ein Fehlercode.  Wenn der eingegebene Zeiger `randomValue` ein NULL\-Zeiger ist, ruft die Funktion einen ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion `EINVAL` zurück und setzt `errno` auf `EINVAL`.  Wenn die Funktion für einen anderen Grund fehlschlägt, \*`randomValue` auf 0 festgelegt.  
  
## Hinweise  
 Die Funktion `rand_s``UINT_MAX`\-Attribut eine Pseudo\-Zufallsganze Zahl im Bereich von 0 z Eingabezeiger.  Die Funktion `rand_s` verwendet das Betriebssystem, um kryptografisch Zufallszahlen generieren zu speichern.  Es verwendet nicht den Startwert, der durch die [srand](../../c-runtime-library/reference/srand.md)\-Funktion generiert wird, und wirkt sie sich auf die Zufallszahlensequenz, die von `rand` verwendet wird.  
  
 Die Funktion `rand_s` erfordert, dass konstantes `_CRT_RAND_S` vor der Inklusionsanweisung definiert wurde, sodass die Funktion deklariert werden, wie im folgenden Beispiel:  
  
```  
#define _CRT_RAND_S  
#include <stdlib.h>  
```  
  
 `rand_s` hängt von der API ab [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694), die in Windows XP und höher nur verfügbar ist.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`rand_s`|\<stdlib.h\>|  
  
 Weitere Informationen finden Sie unter[Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_rand_s.c  
// This program illustrates how to generate random  
// integer or floating point numbers in a specified range.  
  
// Remembering to define _CRT_RAND_S prior  
// to inclusion statement.  
#define _CRT_RAND_S  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <limits.h>  
  
int main( void )  
{  
    int             i;  
    unsigned int    number;  
    double          max = 100.0;  
    errno_t         err;  
  
    // Display 10 random integers in the range [ 1,10 ].  
    for( i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %u\n", (unsigned int) ((double)number /  
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);  
    }  
  
    printf_s("\n");  
  
    // Display 10 random doubles in [0, max).  
    for (i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %g\n", (double) number /   
                          ((double) UINT_MAX + 1) * max );  
    }  
}  
```  
  
## Beispielausgabe  
  
```  
10  
4  
5  
2  
8  
2  
5  
6  
1  
1  
  
32.6617  
29.4471  
11.5413  
6.41924  
20.711  
60.2878  
61.0094  
20.1222  
80.9192  
65.0712  
```  
  
## .NET Framework-Entsprechung  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)