---
title: Generische Delegaten (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2511034af4399c983b8114ec01a86e3290bd2a8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="generic-delegates-visual-c"></a>Generische Delegaten (Visual C++)
Sie können generische Typparameter mit Delegaten verwenden. Weitere Informationen zu Delegaten finden Sie unter [Delegate (Komponentenerweiterungen für C++)](../windows/delegate-cpp-component-extensions.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
[attributes]   
generic < [class | typename] type-parameter-identifiers >  
[type-parameter-constraints-clauses]  
[accessibility-modifiers] delegate result-type identifier   
([formal-parameters]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `attributes`(Optional)  
 Zusätzliche deklarative Informationen. Weitere Informationen zu Attributen und Attributklassen finden Sie unter "Attribute".  
  
 *Type-Parameter-Bezeichner*  
 Durch Trennzeichen getrennte Liste der Bezeichner für die Typparameter.  
  
 `type-parameter-constraints-clauses`  
 Hat das Format im angegebenen [Einschränkungen für generische Typparameter (C + c++ / CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)  
  
 *Zugriffsmodifizierer* (Optional)  
 Zugriffsmodifizierer (z. B. **öffentlichen**, `private`).  
  
 *Ergebnistyp*  
 Der Rückgabetyp des Delegaten.  
  
 *identifier*  
 Der Name des Delegaten.  
  
 *formaler Parameter* (Optional)  
 Die Parameterliste des Delegaten.  
  
## <a name="example"></a>Beispiel  
 Die Typparameter des Delegaten werden am Punkt angegeben, in dem ein Delegatobjekt erstellt wird. Sowohl der Delegat als auch die Methode, die mit ihm verknüpften müssen die gleiche Signatur haben. Im folgenden ist ein Beispiel für eine Deklaration einer generischen Delegaten.  
  
```  
// generics_generic_delegate1.cpp  
// compile with: /clr /c  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, die  
  
-   Sie können nicht das gleiche Delegatobjekt mit verschiedenen konstruierte Typen verwenden. Erstellen Sie-Delegaten-Objekte für verschiedene Arten.  
  
-   Ein generischer Delegat kann einer generischen Methode zugeordnet werden.  
  
-   Wenn eine generische Methode ohne Angabe der Typargumente aufgerufen wird, versucht der Compiler die Typargumente für den Aufruf abzuleiten.  
  
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
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird einen generischer Delegat deklariert `GenDelegate<ItemType>`, und es dann durch die Zuordnung von es an die Methode instanziiert `MyMethod` , verwendet den Typparameter `ItemType`. Zwei Instanzen des Delegaten (Integer und Double) erstellt und aufgerufen.  
  
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
  
```Output  
Invoking the integer delegate: i = 123, j = 123  
Invoking the double delegate: m = 0.123, n = 0.123  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Generika](../windows/generics-cpp-component-extensions.md)