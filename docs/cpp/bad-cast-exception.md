---
title: Bad_cast-Ausnahme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bad_cast
- bad_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- exceptions, bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 70758ca099853f94ad06b8a9f5029203a480a772
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="badcast-exception"></a>bad_cast-Ausnahme
Die `bad_cast`-Ausnahme wird vom `dynamic_cast`-Operator als Folge eines Fehlers bei der Umwandlung in einen Verweistyp ausgelöst.  
  
## <a name="syntax"></a>Syntax  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>Hinweise  
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
  
 Die Ausnahme wird ausgelöst, weil das umgewandelte Objekt (eine Form) nicht vom angegebenen Umwandlungstyp (Kreis) abgeleitet wird. Um die Ausnahme zu vermeiden, fügen Sie `main` diese Deklarationen hinzu:  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Kehren Sie dann den Sinn der Umwandlung im `try`-Block wie folgt um:  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Dynamic_cast-Operator](../cpp/dynamic-cast-operator.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)
