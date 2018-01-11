---
title: _ReturnAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _ReturnAddress
dev_langs: C++
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d207fcba6846d0a5e599d6273f5b35bb554bda40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="returnaddress"></a>_ReturnAddress
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die `_ReturnAddress` systeminterne stellt die Adresse der Anweisung in der aufrufenden Funktion, die ausgeführt wird, nachdem die Steuerung an den Aufrufer zurückgibt.  
  
 Erstellen Sie das folgende Programm und die schrittweise durchlaufen im Debugger. Beachten Sie die Adresse, die von zurückgegeben wird, während Sie die Anwendung durchlaufen, `_ReturnAddress`. Klicken Sie dann sofort nach der Rückgabe der Funktion, in denen `_ReturnAddress` wurde, verwendet wird, öffnen die [wie: Verwenden des Fensters Disassembly](/visualstudio/debugger/how-to-use-the-disassembly-window) , und beachten Sie, dass die Adresse des nächsten auszuführenden die Adresse von zurückgegebenenübereinstimmt`_ReturnAddress`.  
  
 Optimierungen, wie z. B. inlining möglicherweise Auswirkungen auf die Rückgabeadresse. Angenommen, das folgende Beispielprogramm mit kompiliert wird [/Ob1](../build/reference/ob-inline-function-expansion.md), `inline_func` werden inline in der aufrufenden Funktion `main`. Aus diesem Grund die Aufrufe von `_ReturnAddress` aus `inline_func` und `main` wird jeweils den gleichen Wert zu erzeugen.  
  
 Wenn `_ReturnAddress` wird verwendet, in einem Programm kompiliert mit ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md), die Funktion mit der `_ReturnAddress` Aufruf wird als eine systemeigene Funktion kompiliert werden. Wenn eine Funktion kompiliert, als verwaltete Aufrufe an die Funktion mit `_ReturnAddress`, `_ReturnAddress` verhält sich möglicherweise nicht wie erwartet.  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<intrin.h >  
  
## <a name="example"></a>Beispiel  
  
```  
// compiler_intrinsics__ReturnAddress.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_ReturnAddress)  
  
__declspec(noinline)  
void noinline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
__forceinline  
void inline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
int main(void)  
{  
   noinline_func();   
   inline_func();  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
  
   return 0;  
}  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)