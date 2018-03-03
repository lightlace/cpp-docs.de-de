---
title: Typeid-Operator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b27f3bcb7358b3ea05907df1a4372c107538dfb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="typeid-operator"></a>typeid-Operator
## <a name="syntax"></a>Syntax  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## <a name="remarks"></a>Hinweise  
 Der `typeid`-Operator ermöglicht, den Typ eines Objekts zur Laufzeit zu bestimmen.  
  
 Das Ergebnis des `typeid` ist ein **const Type_info &**. Der Wert ist ein Verweis auf eine **Type_info** Objekt, das entweder darstellt der *Typ-Id* oder den Typ des der *Ausdruck*, je nachdem, welche Form von `typeid` verwendet wird . Finden Sie unter [Type_info-Klasse](../cpp/type-info-class.md) für Weitere Informationen.  
  
 Die `typeid` Operator funktioniert nicht mit verwalteten Typen (abstrakte Deklaratoren oder Instanzen), finden Sie unter [Typeid](../windows/typeid-cpp-component-extensions.md) Informationen zum Abrufen der <xref:System.Type> eines angegebenen Typs.  
  
 Der `typeid`-Operator führt eine Laufzeitüberprüfung durch, wenn er auf einen l-Wert eines polymorphen Klassentyps angewendet wird, bei dem der Objekttyp nicht anhand der statischen Informationen bestimmt werden kann. Zu solchen Fällen zählen folgende:  
  
-   Ein Verweis auf eine Klasse  
  
-   Ein Zeiger, durch * dereferenziert  
  
-   Ein indizierter Zeiger (d. h. [ ]). (Beachten Sie, dass es im Allgemeinen nicht sicher ist, einen Index mit einem Zeiger auf einen polymorphen Typ zu verwenden.)  
  
 Wenn die *Ausdruck* auf einen Basisklassentyp verweist, noch das Objekt tatsächlich ein Typ, der von dieser Basisklasse abgeleitet ist ein **Type_info** verweisen, für die abgeleitete Klasse das Ergebnis ist. Die *Ausdruck* muss auf einen polymorphen Typ (eine Klasse mit virtuellen Funktionen) verweisen. Das Ergebnis, andernfalls ist der **Type_info** für die statische Klasse, die gemäß der *Ausdruck*. Darüber hinaus muss der Zeiger dereferenziert werden, sodass das Objekt, auf das er zeigt, verwendet wird. Ohne Dereferenzierung des Zeigers ist das Ergebnis werden die **Type_info** für den Zeiger, verweist nicht auf. Zum Beispiel:  
  
```  
// expre_typeid_Operator.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <typeinfo.h>  
  
class Base {  
public:  
   virtual void vvfunc() {}  
};  
  
class Derived : public Base {};  
  
using namespace std;  
int main() {  
   Derived* pd = new Derived;  
   Base* pb = pd;  
   cout << typeid( pb ).name() << endl;   //prints "class Base *"  
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"  
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"  
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"  
   delete pd;  
}  
```  
  
 Wenn die *Ausdruck* ist einen Zeiger dereferenziert und den Wert des Zeigers auf 0 (null), ist **Typeid** löst eine [Bad_typeid-Ausnahme](../cpp/bad-typeid-exception.md). Wenn der Zeiger nicht auf ein gültiges Objekt verweist eine `__non_rtti_object` Ausnahme ausgelöst wird, wird, der angibt, der Versuch, den RTTI analysieren, die einen Fehler ausgelöst (z. B. zugriffsverletzung), da das Objekt aus irgendeinem Grund ungültig ist (ungültiger Zeiger oder der Code wurde nicht kompiliert mit [/Gr](../build/reference/gr-enable-run-time-type-information.md)).  
  
 Wenn die *Ausdruck* ist weder ein Zeiger noch ein Verweis auf eine Basisklasse des Objekts, das Ergebnis ist ein **Type_info** Verweis, der den statischen Typ des darstellt der *Ausdruck*. Die *statischen Typ* eines Ausdrucks verweist auf den Typ eines Ausdrucks, da es zum Zeitpunkt der Kompilierung bekannt ist. Die Ausführungssemantik wird ignoriert, wenn der statische Typ eines Ausdrucks bewertet wird. Außerdem werden wenn möglich Verweise ignoriert, wenn der statische Typ eines Ausdrucks bestimmt wird:  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **Typeid** kann auch in Vorlagen zum Bestimmen des Typs eines Vorlagenparameters verwendet werden:  
  
```  
// expre_typeid_Operator_3.cpp  
// compile with: /c  
#include <typeinfo>  
template < typename T >   
T max( T arg1, T arg2 ) {  
   cout << typeid( T ).name() << "s compared." << endl;  
   return ( arg1 > arg2 ? arg1 : arg2 );  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeit-Typinformationen](../cpp/run-time-type-information.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)