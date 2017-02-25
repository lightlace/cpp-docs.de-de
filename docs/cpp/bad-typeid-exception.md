---
title: "bad_typeid-Ausnahme | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "bad_typeid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_typeid-Ausnahme"
  - "Ausnahmen, bad_typeid"
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# bad_typeid-Ausnahme
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Ausnahme `bad_typeid` wird von [typeid operator](../cpp/typeid-operator.md) ausgelöst, wenn der Operand für `typeid` ein NULL\-Zeiger ist.  
  
## Syntax  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## Hinweise  
 Die Schnittstelle für `bad_typeid` ist:  
  
```  
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 Im folgenden Beispiel wird der `typeid`\-Operators gezeigt, der eine `bad_typeid`\-Ausnahme auslöst.  
  
```  
// expre_bad_typeid.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class A{  
public:  
   // object for class needs vtable  
   // for RTTI  
   virtual ~A();  
};  
  
using namespace std;  
int main() {  
A* a = NULL;  
  
try {  
   cout << typeid(*a).name() << endl;  // Error condition  
   }  
catch (bad_typeid){  
   cout << "Object is NULL" << endl;  
   }  
}  
```  
  
## Ausgabe  
  
```  
Object is NULL  
```  
  
## Siehe auch  
 [Laufzeit\-Typinformationen](../cpp/run-time-type-information.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)