---
title: "deprecated (C/C++)"
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
  - "vc-pragma.deprecated"
  - "deprecated_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "deprecated-Pragma"
  - "Pragmas, deprecated"
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# deprecated (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Pragma **deprecated** ermöglicht es Ihnen anzugeben, dass eine Funktion, ein Typ oder ein anderer Bezeichner in einer zukünftigen Version möglicherweise nicht mehr unterstützt wird oder nicht mehr verwendet werden sollte.  
  
## Syntax  
  
```  
  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## Hinweise  
 Wenn der Compiler ein veraltetes Symbol findet, gibt er [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md) aus.  
  
 Sie können Makronamen als veraltet deklarieren.  Platzieren Sie den Makronamen in Anführungszeichen; andernfalls tritt eine Makroerweiterung auf.  
  
 Der Modifizierer [deprecated](../cpp/deprecated-cpp.md) `__declspec` ermöglicht es Ihnen, den veralteten Zustand von bestimmten Formen überladener Funktionen zu bestimmen.  
  
## Beispiel  
  
```  
// pragma_directive_deprecated.cpp  
// compile with: /W3  
#include <stdio.h>  
void func1(void) {  
}  
  
void func2(void) {  
}  
  
int main() {  
   func1();  
   func2();  
   #pragma deprecated(func1, func2)  
   func1();   // C4995  
   func2();   // C4995  
}  
```  
  
 Das folgende Beispiel zeigt, wie Sie eine Klasse als veraltet deklarieren:  
  
```  
// pragma_directive_deprecated2.cpp  
// compile with: /W3  
#pragma deprecated(X)  
class X {  // C4995  
public:  
   void f(){}  
};  
  
int main() {  
   X x;   // C4995  
}  
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)