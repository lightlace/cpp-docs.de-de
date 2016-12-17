---
title: "bad_cast-Ausnahme"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "bad_cast"
  - "bad_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_cast-Schlüsselwort [C++]"
  - "Ausnahmen, bad_cast"
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# bad_cast-Ausnahme
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `bad_cast`\-Ausnahme wird vom `dynamic_cast`\-Operator als Folge eines Fehlers bei der Umwandlung in einen Verweistyp ausgelöst.  
  
## Syntax  
  
```  
catch (bad_cast)  
   statement  
```  
  
## Hinweise  
 Die Schnittstelle für `bad_cast` ist:  
  
```  
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 Der folgende Code enthält ein Beispiel eines Fehlers bei `dynamic_cast`, der die Ausnahme `bad_cast` auslöst.  
  
```  
// expre_bad_cast_Exception.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
class Circle: public Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
using namespace std;  
int main() {  
   Shape shape_instance;  
   Shape& ref_shape = shape_instance;  
   try {  
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);   
   }  
   catch (bad_cast b) {  
      cout << "Caught: " << b.what();  
   }  
}  
```  
  
 Die Ausnahme wird ausgelöst, weil das umgewandelte Objekt \(eine Form\) nicht vom angegebenen Umwandlungstyp \(Kreis\) abgeleitet wird.  Um die Ausnahme zu vermeiden, fügen Sie `main` diese Deklarationen hinzu:  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Kehren Sie dann den Sinn der Umwandlung im `try`\-Block wie folgt um:  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## Siehe auch  
 [dynamic\_cast\-Operator](../cpp/dynamic-cast-operator.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)