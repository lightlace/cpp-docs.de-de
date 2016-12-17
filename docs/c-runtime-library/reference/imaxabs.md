---
title: "imaxabs"
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
  - "imaxabs"
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
  - "imaxabs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "imaxabs-Funktion"
ms.assetid: de2566a3-1415-4e9a-91b5-7ac3a49ebf5e
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# imaxabs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den absoluten Wert einer ganzen Zahl beliebiger Größe.  
  
## Syntax  
  
```  
intmax_t imaxabs(  
   intmax_t n   
);  
```  
  
#### Parameter  
 *n*  
 Ganzzahliger Wert.  
  
## Rückgabewert  
 Die `imaxabs`\-Funktion gibt den absoluten Wert des Arguments zurück.  Es gibt keine Fehlerrückgabe.  
  
> [!NOTE]
>  Da der mithilfe von `intmax_t` darstellbare Bereich von negativen ganzen Zahlen größer als der entsprechende Bereich von positiven ganzen Zahlen ist, die mithilfe dieses Typs dargestellt werden können, kann für `imaxabs` ein nicht konvertierbares Argument bereitgestellt werden.  Wenn der absolute Wert des Arguments nicht durch den Rückgabetyp dargestellt werden kann, wird das Verhalten von `imaxabs` nicht definiert.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`imaxabs`|\<inttypes.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_imaxabs.c  
// Build using: cl /W3 /Tc crt_imaxabs.c  
// This example calls imaxabs to compute an  
// absolute value, then displays the results.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <inttypes.h>  
  
int main(int argc, char *argv[])  
{  
   intmax_t x = LLONG_MIN + 2;  
  
   printf("The absolute value of %lld is %lld\n", x, imaxabs(x));  
}  
```  
  
  **Der absolute Wert von – 9223372036854775806 ist 9223372036854775806**   
## .NET Framework-Entsprechung  
 [System::Math::Abs](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Abs, Labs, Llabs, \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [Fabs, Fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [labs, llabs](../../misc/labs-llabs.md)