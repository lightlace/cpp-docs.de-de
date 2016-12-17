---
title: "_ReturnAddress"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_ReturnAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReturnAddress (systemintern)"
  - "ReturnAddress (systemintern)"
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# _ReturnAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Systeminterne `_ReturnAddress` stellt die Adresse der Anweisung in der aufrufenden Funktion, die ausgeführt wird, nachdem die Steuerung an den Aufrufer zurückkehrt.  
  
 Erstellen Sie das folgende Programm und den Schritt durch sie im Debugger.  Wie Sie durch das Programm schrittweise ausführen, beachten Sie die Adresse, die von `_ReturnAddress`zurückgegeben wurde.  Dann direkt nach der Rückgabe der Funktion, in der `_ReturnAddress` verwendet wurde, öffnen Sie [Gewusst wie: Verwenden des Fensters Disassembly](../Topic/How%20to:%20Use%20the%20Disassembly%20Window.md) , und beachten Sie, dass die Adresse der nächsten Anweisung ausgeführte Übereinstimmungen zu kommunizieren, die die Adresse von `_ReturnAddress`zurückgibt.  
  
 Optimierungen wie das Inlining beeinflussen möglicherweise die Rückgabeadresse.  Wenn z. B. das folgende Beispielprogramm mit [\/Ob1](../build/reference/ob-inline-function-expansion.md)kompiliert wird, ist `inline_func` in die aufrufende Funktion inline `main`.  Daher sind die Aufrufe `_ReturnAddress` von `inline_func` und `main` jedes Erzeugnis der gleiche Wert.  
  
 Wenn `_ReturnAddress` in einem Programm verwendet wird, die mit [\/clr](../build/reference/clr-common-language-runtime-compilation.md)kompiliert wird, wird die Funktion, die den `_ReturnAddress` Aufruf enthält, als systemeigene Funktion kompiliert.  Wenn eine Funktion, die als verwaltete Aufrufe in die Funktion enthält `_ReturnAddress`kompiliert wird, `_ReturnAddress` sich nicht wie erwartet verhält.  
  
## Anforderungen  
 **Headerdatei** \<intrin.h\>  
  
## Beispiel  
  
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
  
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [\_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)