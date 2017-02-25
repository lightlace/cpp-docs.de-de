---
title: "typeid-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typeid-Operator"
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# typeid-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## Hinweise  
 Der `typeid`\-Operator ermöglicht, den Typ eines Objekts zur Laufzeit zu bestimmen.  
  
 Das Ergebnis von `typeid` ist **const type\_info&**.  Der Wert ist ein Verweis auf ein **type\_info**\-Objekt, das entweder *type\-id* oder den *expression*\-Typ darstellt, abhängig von der verwendeten `typeid`\-Form.  Weitere Informationen finden Sie unter [type\_info\-Klasse](../cpp/type-info-class.md).  
  
 Der `typeid`\-Operator funktioniert nicht mit verwalteten Typen \(abstrakten Deklaratoren oder Instanzen\). Weitere Informationen zum Abrufen von <xref:System.Type> für einen bestimmten Typ finden Sie unter [typeid](../windows/typeid-cpp-component-extensions.md).  
  
 Der `typeid`\-Operator führt eine Laufzeitüberprüfung durch, wenn er auf einen l\-Wert eines polymorphen Klassentyps angewendet wird, bei dem der Objekttyp nicht anhand der statischen Informationen bestimmt werden kann.  Zu solchen Fällen zählen folgende:  
  
-   Ein Verweis auf eine Klasse  
  
-   Ein Zeiger, durch \* dereferenziert  
  
-   Ein indizierter Zeiger \(d. h. \[ \]\). \(Beachten Sie, dass es im Allgemeinen nicht sicher ist, einen Index mit einem Zeiger auf einen polymorphen Typ zu verwenden.\)  
  
 Wenn *expression* auf einen Basisklassentyp verweist, das Objekt aber von einem Typ ist, der von dieser Basisklasse abgeleitet wird, ist das Ergebnis ein **type\_info**\-Verweis auf die abgeleitete Klasse.  *expression* muss auf einen polymorphen Typ zeigen \(eine Klasse mit virtuellen Funktionen\).  Andernfalls ist das Ergebnis die **type\_info** für die statische Klasse, auf die in *expression* verwiesen wird.  Darüber hinaus muss der Zeiger dereferenziert werden, sodass das Objekt, auf das er zeigt, verwendet wird.  Ohne Dereferenzierung des Zeigers ist das Ergebnis die **type\_info** für den Zeiger, jedoch nicht dessen Ziel.  Beispiel:  
  
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
  
 Wenn *expression* einen Zeiger dereferenziert und der Zeigerwert 0 \(null\) ist, löst **typeid** eine [bad\_typeid\-Ausnahme](../cpp/bad-typeid-exception.md) aus.  Wenn der Zeiger nicht auf ein gültiges Objekt verweist, wird eine `__non_rtti_object`\-Ausnahme ausgelöst. Dies weist auf den Versuch hin, die Laufzeit\-Typeninformation \(Run\-time Type Information, RTTI\) zu analysieren, die einen Fehler \(z. B. eine Zugriffsverletzung\) ausgelöst hat, weil das Objekt in irgendeiner Weise ungültig ist \(ein ungültiger Zeiger, oder der Code wurde nicht mit [\/GR](../build/reference/gr-enable-run-time-type-information.md) kompiliert\).  
  
 Wenn *expression* weder ein Zeiger noch ein Verweis auf eine Basisklasse des Objekts ist, ist das Ergebnis ein **type\_info**\-Verweis, der den statischen Typ der *expression* darstellt.  Der *static type* eines Ausdrucks bezeichnet den Ausdruckstyp wie zur Kompilierungszeit bekannt.  Die Ausführungssemantik wird ignoriert, wenn der statische Typ eines Ausdrucks bewertet wird.  Außerdem werden wenn möglich Verweise ignoriert, wenn der statische Typ eines Ausdrucks bestimmt wird:  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **typeid** kann auch in Vorlagen verwendet werden, um den Typ eines Vorlagenparameters zu bestimmen:  
  
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
  
## Siehe auch  
 [Laufzeit\-Typinformationen](../cpp/run-time-type-information.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)