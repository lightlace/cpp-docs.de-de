---
title: Fenv_access | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f06c699ba20d09ec1d013f9464af02935da9f9c1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="fenvaccess"></a>fenv_access
Deaktiviert (AUS) oder aktiviert (EIN) Optimierungen, die Flagtests und Modusänderung ändern könnten.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig ist `fenv_access` AUS.  
  
 Weitere Informationen zu Gleitkommaverhalten, finden Sie unter [/fp (Festlegen von Floating-Verhalten)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Die Arten von Optimierungen, die `fenv_access` unterliegen, lauten:  
  
-   Globale allgemeine Teilausdruckbeseitigung  
  
-   Codebewegung  
  
-   Konstantenfaltung  
  
 Andere Gleitkommapragmas umfassen:  
  
-   [float_control](../preprocessor/float-control.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
out=9.999999776482582e-003  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel steht für Compiler, die Ausgabedateien für Itanium-Prozessoren erzeugen. **/ fp: präzise** hält die Zwischenergebnisse in der erweiterten Genauigkeit, in denen Werte größer als flt_max sind (3. 402823466e + 38F) berechnet werden können und aufgrund dieser Summe Ergebnis von 1,0 haben, wie er es, wenn es manuell berechnet sollte. **/ fp: strict** hält Zwischenergebnisse in ihrer quellgenauigkeit (Float), damit die erste Addition unendlich ist, erzeugt, die im gesamten Ausdruck beibehalten wird.  
  
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
  
```Output  
1.000000  
```  
  
## <a name="example"></a>Beispiel  
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
  
```Output  
out=1.000000000000000e-002  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)