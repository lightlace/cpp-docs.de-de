---
title: "Compilerfehler C2782"
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
  - "C2782"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2782"
ms.assetid: 8b685422-294d-4f64-9f3d-c14eaf03a93d
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2782
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Deklaration': Vorlagenparameter 'Bezeichner' ist mehrdeutig  
  
 Der Compiler kann den Typ eines Vorlagenarguments nicht feststellen.  
  
 Im folgenden Beispiel wird C2782 generiert:  
  
```  
// C2782.cpp  
template<typename T>  
void f(T, T) {}  
  
int main() {  
   f(1, 'c');   // C2782  
   // try the following line instead  
   // f<int>(1, 'c');  
}  
```  
  
 C2782 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2782b.cpp  
// compile with: /clr  
generic<typename T> void gf(T, T) { }  
  
int main() {  
   gf(1, 'c'); // C2782  
   // try the following line instead  
   // gf<int>(1, 'c');  
}  
```