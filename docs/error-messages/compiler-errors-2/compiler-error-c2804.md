---
title: "Compilerfehler C2804"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2804"
ms.assetid: b066e563-cca4-450c-8ba7-3b0d7a89f3ea
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Binärer Operator "Operator" hat zu viele Parameter  
  
 Die überladene binäre Operator\-Memberfunktion wird mit mehr als einem Parameter deklariert.  Der erste Parameter für Operanden einer binären Operator\-Memberfunktion, deren Typ des Operators ist einschließender Typ ist, wird impliziert.  
  
## Beispiel  
 Im folgenden Beispiel wird C2804 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2804.cpp  
// compile by using: cl /c /W4 C2804.cpp  
class X {  
public:  
   X& operator+= (const X &left, const X &right);   // C2804  
   X& operator+= (const X &right);   // OK - left operand implicitly *this  
};  
  
int main() {  
   X x, y;  
   x += y;   // equivalent to x.operator+=(y)  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2804 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2804_2.cpp  
// compile with: /clr /c  
ref struct Y {  
   Y^ operator +(Y^ hY, int i);   // C2804  
   static Y^ operator +(Y^ hY, int i);   // OK  
   Y^ operator +(int i);   // OK  
};  
```