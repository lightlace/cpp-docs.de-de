---
title: "ldiv, lldiv"
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
  - "ldiv"
  - "lldiv"
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
  - "ldiv"
  - "lldiv"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Berechnen von Quotienten"
  - "Berechnen von Restwerten"
  - "ldiv-Funktion"
  - "lldiv-Funktion"
  - "Quotienten, Berechnen"
  - "Restwerte berechnen"
ms.assetid: 68ab5d83-27a4-479c-9d52-d055eb139eca
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# ldiv, lldiv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den Quotienten und den Rest von zwei ganzen Zahlen als eine Operation.  
  
## Syntax  
  
```  
ldiv_t ldiv(  
   long numer,  
   long denom   
);  
lldiv_t lldiv(  
   long long numer,  
   long long denom   
);  
```  
  
#### Parameter  
 `numer`  
 Zähler.  
  
 `denom`  
 Nenner.  
  
## Rückgabewert  
 `ldiv` gibt eine Struktur des Typs [ldiv\_t](../../c-runtime-library/standard-types.md) zurück, die sowohl den Quotienten als auch den Rest enthält.  `lldiv` gibt eine Struktur des Typs [lldiv\_t](../../c-runtime-library/standard-types.md) zurück, die sowohl den Quotienten als auch den Rest enthält.  
  
## Hinweise  
 Die Funktionen `ldiv` und `lldiv` teilen `numer` durch `denom` und berechnen dadurch den Quotienten und den Rest.  Das Zeichen des Quotienten entspricht dem Zeichen des mathematischen Quotienten.  Der absolute Wert des Quotienten ist die größte ganze Zahl, die kleiner ist als der absolute Wert des mathematischen Quotienten.  Wenn der Nenner 0 ist, wird das Programm mit einer Fehlermeldung beendet.  `ldiv` und `lldiv` sind nahezu identisch `div`, außer dass die Argumente von `ldiv` und die Mitglieder der zurückgegebene Struktur alle vom `long`\-Typ sind, die Argumente von `lldiv` und die Mitglieder der zurückgegebenen Struktur jedoch vom `long long`\-Typ sind.  
  
 Die Strukturen `ldiv_t` und `lldiv_t` werden in \<stdlib.h\> definiert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`ldiv`, `lldiv`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_ldiv.c  
  
#include <stdlib.h>  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   long x = 5149627, y = 234879;  
   ldiv_t div_result;  
  
   div_result = ldiv( x, y );  
   printf( "For %ld / %ld, the quotient is ", x, y );  
   printf( "%ld, and the remainder is %ld\n",   
            div_result.quot, div_result.rem );  
}  
```  
  
## Ausgabe  
  
```  
For 5149627 / 234879, the quotient is 21, and the remainder is 217168  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)