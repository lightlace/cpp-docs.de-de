---
title: "remquo, remquof, remquol | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "remquof"
  - "remquo"
  - "remquol"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "remquof"
  - "remquol"
  - "remquo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remquol-Funktion"
  - "remquof-Funktion"
  - "remquo-Funktion"
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# remquo, remquof, remquol
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den Rest von zwei ganzzahligen Werten und speichert einen ganzzahligen Wert mit dem Zeichen und der ungefähren Größe des Quotienten an einem Speicherort, der in einem Parameter angegeben ist.  
  
## Syntax  
  
```  
double remquo(   
   double numer,  
   double denom,  
   int* quo  
);  
float remquo(   
   float numer,  
   float denom,  
   int* quo  
); /* C++ only */  
long double remquo(   
   long double numer,  
   long double denom,  
   int* quo  
); /* C++ only */  
float remquof(   
   float numer,  
   float denom,  
   int* quo  
);  
long double remquol(   
   long double numer,  
   long double denom,  
   int* quo  
);  
  
```  
  
#### Parameter  
 `numer`  
 Der Zähler.  
  
 `denom`  
 Der Nenner.  
  
 `quo`  
 Ein Zeiger auf eine ganze Zahl zum Speichern eines Werts, der das Zeichen und die ungefähre Größe des Quotienten hat.  
  
## Rückgabewert  
 `remquo` gibt den Gleitkommarest von `x` \/ `y` zurück.  Wenn der Wert von `y` 0,0 ist, gibt `remquo` ein stilles NaN zurück.  Informationen über die Darstellung eines stillen NaN durch die `printf`\-Familie finden Sie unter [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## Hinweise  
 Die `remquo`\-Funktion berechnet den Gleitkommarest `f` von `x` \/ `y` wie etwa `x` \= `i` `*` `y` \+ `f`, wobei `i` eine ganze Zahl ist, `f` das gleiche Zeichen wie `x` hat und der absolute Wert von `f` kleiner ist als der absolute Wert von `y`.  
  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `remquo` aufrufen, die `float`\- oder `long double`\-Werte verwenden und zurückgeben.  In einem C\-Programm verwendet `remquo` immer zwei Double und gibt einen Double zurück.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`remquo`, `remquof`, `remquol`|\<math.h\>|  
  
 Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```c  
// crt_remquo.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
   int quo = 0;  
  
   z = remquo(w, x, &quo);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
   printf("Approximate signed quotient is %d\n", quo);  
}  
```  
  
  **Der Rest von – 10.00 \/ 3.00 ist – 1,000000**  
**Der ungefähre signierte Quotient ist – 3**   
## .NET Framework-Entsprechung  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)