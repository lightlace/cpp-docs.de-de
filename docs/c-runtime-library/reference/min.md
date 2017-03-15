---
title: "__min | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__min"
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
apitype: "DLLExport"
f1_keywords: 
  - "__min"
  - "min"
  - "_min"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__min-Makro"
  - "_min-Makro"
  - "min-Makro"
  - "minimum-Makro"
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# __min
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die kleinere von zwei Werten zurück.  
  
## Syntax  
  
```  
type __min(  
   type a,  
   type b   
);  
```  
  
#### Parameter  
 `type`  
 Ein beliebiger numerischer Datentyp.  
  
 `a, b`  
 Werte eines zu vergleichenden numerischen Typs.  
  
## Rückgabewert  
 Das kleinere der zwei Argumente.  
  
## Hinweise  
 Das Makro `__min` vergleicht zwei Werte und gibt den Wert aus dem kleineren zurück.  Die Argumente können von einem beliebigen numerischen Datentyp sein, mit oder ohne Vorzeichen.  müssen Argumente und der Rückgabewert dem gleichen Datentyp.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`__min`|\<stdlib.h\>|  
  
## Beispiel  
  
```  
// crt_minmax.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int a = 10;  
   int b = 21;  
  
   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );  
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );  
}  
```  
  
  **Das größere von 10 und 21 ist 21**  
**Das kleinere von 10 und 21 ist 10**   
## .NET Framework-Entsprechung  
 [System::Math::Min](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [\_\_max](../../c-runtime-library/reference/max.md)