---
title: "__noop | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__noop_cpp"
  - "__noop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__noop-Schlüsselwort [C++]"
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __noop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Systeminterne `__noop` gibt an, dass eine Funktion ignoriert werden sollen und die Argumentliste analysiert wird, aber kein Code für die Argumente generiert wird.  Sie ist für die Verwendung in globalen Funktionen Debuggen bestimmt, die eine variable Anzahl von Argumenten akzeptieren.  
  
 Der Compiler konvertiert `__noop` , das bis 0 zur Kompilierzeit systemintern ist.  
  
## Beispiel  
 Der folgende Code zeigt, wie Sie `__noop`verwenden können.  
  
```  
// compiler_intrinsics__noop.cpp  
// compile with or without /DDEBUG  
#include <stdio.h>  
  
#if DEBUG  
   #define PRINT   printf_s  
#else  
   #define PRINT   __noop  
#endif  
  
int main() {  
   PRINT("\nhello\n");  
}  
```  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)