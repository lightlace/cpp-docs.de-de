---
title: "Compilerfehler C2682"
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
  - "C2682"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2682"
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2682
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

casting\_operator kann nicht zum Konvertieren von 'Typ1' in 'Typ2' verwendet werden  
  
 Ein Umwandlungsoperator hat versucht, eine Konvertierung zwischen inkompatiblen Typen durchzuführen.  Sie können den Operator [dynamic\_cast](../../cpp/dynamic-cast-operator.md) z. B. nicht verwenden, um einen Zeiger in einen Verweis zu konvertieren.  Der Operator `dynamic_cast` kann nicht verwendet werden, um Qualifizierer umzuwandeln.  Alle Qualifizierer für die Typen müssen zueinander passen.  
  
 Sie können den Operator `const_cast` verwenden, um Attribute \(z. B. `const`, `volatile` oder `__unaligned`\) zu entfernen.  
  
 Im folgenden Beispiel wird C2682 generiert:  
  
```  
// C2682.cpp  
class A { virtual void f(); };  
class B: public A {};  
  
void g(A* pa) {  
    B& rb = dynamic_cast<B&>(pa); // C2682  
}  
```  
  
 Im folgenden Beispiel wird C2682 generiert:  
  
```  
// C2682b.cpp  
// compile with: /clr  
ref struct R{};  
ref struct RR : public R{};  
ref struct H {  
   RR^ r ;  
   short s;  
   int i;  
};  
  
int main() {  
   H^ h = gcnew H();    
   interior_ptr<int>lr = &(h->i);  
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682  
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK  
}  
```