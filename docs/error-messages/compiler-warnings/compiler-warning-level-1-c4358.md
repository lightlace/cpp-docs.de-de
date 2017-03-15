---
title: "Compilerwarnung (Stufe 1) C4358 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4358"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4358"
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4358
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Der Rückgabetyp von kombinierten Delegaten ist nicht 'void'; der zurückgegebene Wert ist nicht definiert  
  
 Zwei Delegaten wurden kombiniert, und der Rückgabewert ist nicht void.  Wenn zwei Delegaten mit Rückgabewerten kombiniert werden, die nicht void sind, kann der Compiler keine richtige Zuweisung vornehmen, falls der Rückgabewert des Delegaten verwendet wird.  
  
 Im folgenden Beispiel wird C4358 generiert:  
  
```  
// C4358.cpp  
// compile with: /clr /W1  
delegate int D();  
delegate void E();  
  
ref class X {  
   int i;  
public:  
   X(int ii) : i(ii) {}  
   int f() {  
      return i;  
   }  
};  
  
ref class Y {  
   int i;  
public:  
   Y() {}  
   void g() {}  
};  
  
int main() {  
   D^ d = gcnew D(gcnew X(1), &X::f);  
   D^ d2 = gcnew D(gcnew X(2), &X::f);  
  
   d += d2;   // C4358  
   int j = d();   // return value indeterminate  
  
   E^ e = gcnew E(gcnew Y, &Y::g);  
   E^ e2 = gcnew E(gcnew Y, &Y::g);  
   e += e2;   // OK  
}  
```