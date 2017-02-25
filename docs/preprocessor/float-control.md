---
title: "float_control | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.float_control"
  - "float_control_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "float_control-Pragma"
  - "Pragmas, float_control"
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# float_control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt Gleitkommaverhalten für eine Funktion an.  
  
## Syntax  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## Flags  
 `value` *,* `setting` **\[push\]**  
 Gibt das Gleitkommaverhalten an.  `value` kann **precise**  oder **except** sein.  Weitere Informationen finden Sie unter [\/fp \(Festlegen des Gleitkommaverhaltens\)](../build/reference/fp-specify-floating-point-behavior.md).  `setting` kann **on** oder **off** sein.  
  
 Wenn `value` **precise** ist, werden die Einstellungen für **precise** und **except** angegeben.  **except** kann nur auf **on**  festgelegt werden, wenn **precise**  auch in **on** festgelegt ist.  
  
 Wenn das optionale **push** \-Token hinzugefügt wird, wird die aktuelle Einstellung für `value` auf dem internen Compilerstapel abgelegt.  
  
 **push**  
 Schieben Sie die aktuelle `float_control`\-Einstellung auf den internen Compilerstapel.  
  
 **pop**  
 Entfernt die`float_control`\-Einstellung aus der obersten Position des internen Compilerstapels und erstellt die neue `float_control`\-Einstellung.  
  
## Hinweise  
 Sie können `float_control precise` nicht deaktivieren, wenn **except** aktiviert ist.  Ebenso kann **precise** nicht deaktiviert werden, wenn `fenv_access` aktiviert ist.  Um mit dem `float_control`\-Pragma vom strict\-Modell zum fast\-Modell überzugehen, verwenden Sie den folgenden Code:  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
// The following line is needed on Itanium processors  
#pragma fp_contract(on)  
```  
  
 Um mit dem `float_control`\-Pragma vom fast\-Modell zum strict\-Modell überzugehen, verwenden Sie den folgenden Code:  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
// The following line is needed on Itanium processors.  
#pragma fp_contract(off)  
```  
  
 Andere Gleitkommapragmas umfassen:  
  
-   [fenv\_access](../preprocessor/fenv-access.md)  
  
-   [fp\_contract](../preprocessor/fp-contract.md)  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine Überlaufgleitkommaausnahme mit dem Pragma `float_control` verwendet wird.  
  
```  
// pragma_directive_float_control.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <float.h>  
  
double func( ) {  
   return 1.1e75;  
}  
  
#pragma float_control (except,on)  
  
int main( ) {  
   float u[1];  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);  
   if (err != 0)  
      printf_s("_controlfp_s failed!\n");  
  
   try  {  
      u[0] = func();  
      printf_s ("Fail");     
      return(1);  
   }   
  
   catch (...)  {  
      printf_s ("Pass");  
      return(0);  
   }  
}  
```  
  
  **Erfolgreich**   
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)