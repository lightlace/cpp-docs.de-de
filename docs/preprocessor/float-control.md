---
title: Float_control | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs:
- C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1525b92b43a688cdec970c646613aa4474d44cc3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="floatcontrol"></a>float_control
Gibt Gleitkommaverhalten für eine Funktion an.  
  
## <a name="syntax"></a>Syntax  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>Flags  
 `value`, `setting` **[push]**  
 Gibt das Gleitkommaverhalten an. `value` kann **präzise** oder **außer**. Weitere Informationen finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../build/reference/fp-specify-floating-point-behavior.md). `setting` kann entweder **auf** oder **deaktiviert**.  
  
 Wenn `value` ist **präzise**, die Einstellungen für **präzise** und **außer** sind angegeben. **mit Ausnahme von** kann nur festgelegt werden, um **auf** beim **präzise** auch **auf**.  
  
 Wenn das optionale **Push** -Token hinzugefügt wird, wird die aktuelle Einstellung für `value` wird verschoben, auf dem internen compilerstapel ab.  
  
 **push**  
 Schieben Sie die aktuelle `float_control`-Einstellung auf den internen Compilerstapel.  
  
 **pop**  
 Entfernt die `float_control` festlegen, die von der obersten Position des internen Compilerstapels und macht das das neue `float_control` Einstellung.  
  
## <a name="remarks"></a>Hinweise  
 Kann nicht `float_control precise` deaktiviert, wenn **außer** befindet sich auf. Auf ähnliche Weise **präzise** kann nicht deaktiviert werden Wenn `fenv_access` befindet sich auf. Um mit dem `float_control`-Pragma vom strict-Modell zum fast-Modell überzugehen, verwenden Sie den folgenden Code:  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
// The following line is needed on Itanium processors  
#pragma fp_contract(on)  
```  
  
 Um mit dem `float_control`-Pragma vom fast-Modell zum strict-Modell überzugehen, verwenden Sie den folgenden Code:  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
// The following line is needed on Itanium processors.  
#pragma fp_contract(off)  
```  
  
 Andere Gleitkommapragmas umfassen:  
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Beispiel  
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
  
```Output  
Pass  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)