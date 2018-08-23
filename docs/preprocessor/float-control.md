---
title: Float_control | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9b94e5b8eccdc63735c7cb25faa7eacb1e23670
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42543140"
---
# <a name="floatcontrol"></a>float_control
Gibt Gleitkommaverhalten für eine Funktion an.  
  
## <a name="syntax"></a>Syntax  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>Flags  
 
*Wert*, *Einstellung* *[Pushbenachrichtigungen]*  
Gibt das Gleitkommaverhalten an. *Wert* kann `precise` oder `except`. Weitere Informationen finden Sie unter [/fp (Festlegen des Gleitkommaverhaltens)](../build/reference/fp-specify-floating-point-behavior.md). *Festlegen von* Optionen sind möglich `on` oder `off`.  
  
Wenn *Wert* ist `precise`, das die Einstellungen für `precise` und `except` angegeben. `except` kann nur festgelegt werden, um `on` beim `precise` nastaven NA hodnotu auch `on`.  
  
Wenn der optionale *Push* -Token hinzugefügt wird, wird die aktuelle Einstellung für *Wert* wird verschoben, auf dem internen compilerstapel ab.  
  
*push*  
Schieben Sie die aktuelle **Float_control** -Einstellung auf dem internen compilerstapel ab  
  
*pop*  
Entfernt die **Float_control** festlegen, die von der obersten Position des internen Compilerstapels und erstellt die neue **Float_control** festlegen.  
  
## <a name="remarks"></a>Hinweise  
 
Sie können `float_control precise` nicht deaktivieren, wenn `except` aktiviert ist. Ebenso kann `precise` nicht deaktiviert werden, wenn `fenv_access` aktiviert ist. Wechseln Sie vom strict-Modell zum fast-Modell mit den **Float_control** Pragma, verwenden Sie den folgenden Code:  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
```  
  
Wechseln Sie vom fast-Modell zum strict-Modell mit den **Float_control** Pragma, verwenden Sie den folgenden Code:  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
```  
  
Andere Gleitkommapragmas umfassen:  
  
- [fenv_access](../preprocessor/fenv-access.md)  
  
- [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Beispiel  
 
Das folgende Beispiel zeigt, wie eine Gleitkomma-Stapelüberlauf-Ausnahme abgefangen wird, mithilfe von Pragma **Float_control**.  
  
```cpp  
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
