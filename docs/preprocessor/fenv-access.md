---
title: "fenv_access | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.fenv_access"
  - "fenv_access_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenv_access-Pragma"
  - "Pragmas, fenv_access"
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# fenv_access
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deaktiviert \(AUS\) oder aktiviert \(EIN\) Optimierungen, die Flagtests und Modusänderung ändern könnten.  
  
## Syntax  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## Hinweise  
 Standardmäßig ist `fenv_access` AUS.  
  
 Weitere Informationen zum Gleitkommaverhalten finden Sie unter [\/fp \(Festlegen des Gleitkommaverhaltens\)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Die Arten von Optimierungen, die `fenv_access` unterliegen, lauten:  
  
-   Globale allgemeine Teilausdruckbeseitigung  
  
-   Codebewegung  
  
-   Konstantenfaltung  
  
 Andere Gleitkommapragmas umfassen:  
  
-   [float\_control](../preprocessor/float-control.md)  
  
-   [fp\_contract](../preprocessor/fp-contract.md)  
  
## Beispiel  
  
```  
// pragma_directive_fenv_access_x86.cpp  
// compile with: /O2  
// processor: x86  
#include <stdio.h>  
#include <float.h>   
#include <errno.h>  
#pragma fenv_access (on)  
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **out\=9.999999776482582e\-003**   
## Beispiel  
 Das folgende Beispiel steht für Compiler, die Ausgabedateien für Itanium\-Prozessoren erzeugen.  **\/fp:precise** hält die Zwischenergebnisse in der erweiterten Genauigkeit, in der die Werte, die größer als FLT\_MAX sind \(3.402823466e\+38F\), berechnet werden können und aufgrund dieser Summe ein Ergebnis von 1,0 haben, wie es sein soll, wenn es manuell berechnet wird.  **\/fp:strict** hält Zwischenergebnisse in ihrer Quellgenauigkeit \(Float\), die erste Addition ergibt also unendlich, was im gesamten Ausdruck beibehalten wird.  
  
```  
// pragma_directive_fenv_access_IPF.cpp  
// compile with: /O2 /fp:precise  
// processor: IPF  
// compiling with /fp:precise prints 1.0F  
// compile with /fp:strict to print infinity  
  
#include <stdio.h>  
float arr[5] = {3.402823465e+38F,   
               3.402823462e+38F,  
               3.402823464e+38F,  
               3.402823463e+38F,  
               1.0F};  
  
int main() {  
   float sum = 0;  
   sum = arr[0] + arr[1] - arr[2] - arr[3] + arr[4];  
   printf_s("%f\n", sum);  
}  
```  
  
  **1.000000**   
## Beispiel  
 Beim Auskommentieren von `#pragma fenv_access (on)` aus dem vorherigen Beispiel beachten Sie, dass die Ausgabe anders ist, da der Compiler eine Kompilierzeitauswertung vornimmt, die nicht den Steuermodus verwendet.  
  
```  
// pragma_directive_fenv_access_2.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>   
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **out\=1.000000000000000e\-002**   
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)