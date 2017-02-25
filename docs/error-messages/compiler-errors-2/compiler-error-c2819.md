---
title: "Compilerfehler C2819 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2819"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2819"
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2819
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typ "Typ" hat keinen überladenen Elementoperator "\-\>"  
  
 Sie müssen `operator->()` definieren, um diese Zeigeroperation verwenden zu können.  
  
 Im folgenden Beispiel wird C2819 generiert:  
  
```  
// C2819.cpp  
// compile with: /c  
class A {  
   public:  
      int i;  
};  
  
class B {};  
  
void C(B j) {  
   j->i;   // C2819  
}  
  
class D {  
   A* pA;  
  
   public:  
      A* operator->() {  
         return pA;  
      }  
};  
  
void F(D j) {  
   j->i;  
}  
```  
  
 C2819 kann auch auftreten, wenn [C\+\+\-Stack\-Semantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md) verwendet wird.  Im folgenden Beispiel wird C2819 generiert:  
  
```  
// C2819_b.cpp  
// compile with: /clr  
ref struct R {  
   void Test() {}  
};  
  
int main() {  
   R r;  
   r->Test();   // C2819  
   r.Test();   // OK  
}  
```