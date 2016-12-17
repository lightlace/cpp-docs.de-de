---
title: "Compilerwarnung (Stufe 3) C4521"
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
  - "C4521"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4521"
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4521
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Mehrere Kopierkonstruktoren angegeben  
  
 Die Klasse verfügt über mehrere Kopierkonstruktoren eines einzelnen Typs.  Diese Warnung dient nur Informationszwecken; die Konstruktoren sind im Programm aufrufbar.  
  
 Verwenden Sie das [warning](../../preprocessor/warning.md)\-Pragma, um diese Warnung zu unterdrücken.  
  
## Beispiel  
 Im folgenden Beispiel wird C4521 generiert.  
  
```  
// C4521.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A() { cout << "A's default constructor" << endl; }  
   A( A &o ) { cout << "A&" << endl; }  
   A( const A &co ) { cout << "const A&" << endl; }   // C4521  
};  
  
int main() {  
   A o1;         // Calls default constructor.  
   A o2( o1 );   // Calls A( A& ).  
   const A o3;   // Calls default constructor.  
   A o4( o3 );   // Calls A( const A& ).  
}  
```