---
title: "Compilerwarnung (Stufe 3) C4522 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4522"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4522"
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 3) C4522
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Mehrere Zuweisungsoperatoren angegeben  
  
 Die Klasse verfügt über mehrere Zuweisungsoperatoren eines einzelnen Typs.  Diese Warnung dient nur Informationszwecken; die Konstruktoren sind im Programm aufrufbar.  
  
 Verwenden Sie das [warning](../../preprocessor/warning.md)\-Pragma, um diese Warnung zu unterdrücken.  
  
## Beispiel  
 Im folgenden Beispiel wird C4522 generiert.  
  
```  
// C4522.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }  
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522  
};  
  
int main() {  
   A o1, o2;  
   o2 = o1;  
   const A o3;  
   o1 = o3;  
}  
```