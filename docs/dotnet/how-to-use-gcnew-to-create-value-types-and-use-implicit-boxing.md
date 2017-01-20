---
title: "Gewusst wie: Verwenden von gcnew zum Erstellen von Werttypen und f&#252;r implizites Boxing"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Boxing, Implizite"
  - "gcnew-Schlüsselwort [C++], Erstellen von Werttypen"
  - "Werttypen, Erstellen"
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von gcnew zum Erstellen von Werttypen und f&#252;r implizites Boxing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) auf einen Werttyp erstellt einen geschachtelten Werttyp, auf das verwaltete dann abgelegt werden kann, aus der Garbage Collection.  
  
## Beispiel  
  
```  
// vcmcppv2_explicit_boxing4.cpp  
// compile with: /clr  
public value class V {  
public:  
   int m_i;  
   V(int i) : m_i(i) {}  
};  
  
public ref struct TC {  
   void do_test(V^ v) {  
      if (v != nullptr)  
         ;  
      else  
         ;  
   }  
};  
  
int main() {  
   V^ v = gcnew V(42);  
   TC^ tc = gcnew TC;  
   tc->do_test(v);  
}  
```  
  
## Siehe auch  
 [Boxing](../windows/boxing-cpp-component-extensions.md)