---
title: "Generic Delegates (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic delegates"
  - "delegates, generic [C++]"
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
caps.latest.revision: 20
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Delegates (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können generische Typparameter mit Delegaten verwenden.  Weitere Informationen über Delegaten, finden Sie unter [delegate](../windows/delegate-cpp-component-extensions.md).  
  
## Syntax  
  
```  
[attributes]   
generic < [class | typename] type-parameter-identifiers >  
[type-parameter-constraints-clauses]  
[accessibility-modifiers] delegate result-type identifier   
([formal-parameters]);  
```  
  
#### Parameter  
 `attributes` \(Optional\)  
 Zusätzliche deklarative Informationen.  Weitere Informationen zu Attributen und Attributklassen, finden Sie Attribute.  
  
 *Typparameterbezeichner*  
 Durch Kommas getrennte Liste von Bezeichnern für die Typparameter.  
  
 `type-parameter-constraints-clauses`  
 Nimmt die Form auf, die in [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) angegeben  
  
 *BarrierefreiheitModifizierer* \(optional\)  
 Zugriffsmodifizierer \(z.  **public**, `private`\).  
  
 *Ergebnistyp*  
 Der Rückgabetyp des Delegaten.  
  
 *Bezeichner \(identifier\)*  
 Der Name des Delegaten.  
  
 *formale Parameter* \(Optional\)  
 Die Parameterliste des Delegaten.  
  
## Beispiel  
 Die Delegattypparameter werden am Punkt, an dem ein Delegatobjekt erstellt wird.  Sowohl der Delegat als auch die Methode, die zugeordnet ist, müssen die gleiche Signatur haben.  Im folgenden Beispiel einer generischen Delegatdeklaration.  
  
```  
// generics_generic_delegate1.cpp  
// compile with: /clr /c  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
```  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, dass  
  
-   Sie können dasselbe Delegatobjekt mit unterschiedlichen generischen Typen nicht verwenden.  Erstellen Sie andere Delegatobjekte für unterschiedliche Typen.  
  
-   Ein generischer Delegat kann mit einer generischen Methode zugeordnet sind.  
  
-   Wenn eine generische Methode aufgerufen wird, ohne Typargumente angeben, versucht der Compiler, die Typargumente für den Aufruf abzuleiten.  
  
```  
// generics_generic_delegate2.cpp  
// compile with: /clr  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
  
generic < class ItemType>  
ref struct MyGenClass {  
   ItemType MyMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
ref struct MyClass {  
   generic < class ItemType>  
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
int main() {  
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();  
   GenDelegate<int>^ myDelegate1 =  
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   GenDelegate<double>^ myDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   GenDelegate<int>^ myDelegate =  
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);  
}  
```  
  
## Beispiel  
 Das folgende Beispiel deklariert einen generischen Delegaten `GenDelegate<ItemType>` und instanziiert ihn, indem die Methode `MyMethod` zugeordnet werden, die den Typparameter `ItemType` verwendet.  Zwei Instanzen des Delegaten \(integer und double\) werden erstellt und aufgerufen.  
  
```  
// generics_generic_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare generic delegate  
generic <typename ItemType>  
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);  
  
// Declare a generic class:  
generic <typename ItemType>  
ref class MyGenClass {  
public:  
   ItemType MyMethod(ItemType p1, ItemType% p2) {  
      p2 = p1;  
      return p1;  
    }  
};  
  
int main() {  
   int i = 0, j = 0;   
   double m = 0.0, n = 0.0;  
  
   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();   
  
   // Instantiate a delegate using int.  
   GenDelegate<int>^ MyDelegate1 =   
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   i = MyDelegate1(123, j);  
  
   Console::WriteLine(  
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);  
  
   // Instantiate a delegate using double.  
   GenDelegate<double>^ MyDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   m = MyDelegate2(0.123, n);  
  
   Console::WriteLine(  
      "Invoking the double delegate: m = {0}, n = {1}", m, n);  
}  
```  
  
  **Aufrufen des ganzzahligen Delegate: I \= 123, J \= 123**  
**Aufrufen des doppelten Delegate: m \= 0,123, n \= 0,123**   
## Siehe auch  
 [Generics](../windows/generics-cpp-component-extensions.md)