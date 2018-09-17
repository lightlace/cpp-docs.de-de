---
title: Generische Delegaten (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a9613dbc28b3e1f263133c15ae88d20294962e9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702532"
---
# <a name="generic-delegates-visual-c"></a>Generische Delegaten (Visual C++)

Sie können generische Typparameter mit Delegaten verwenden. Weitere Informationen zu Delegaten finden Sie unter [Delegate (Komponentenerweiterungen)](../windows/delegate-cpp-component-extensions.md).

## <a name="syntax"></a>Syntax

```cpp
[attributes]
generic < [class | typename] type-parameter-identifiers>
[type-parameter-constraints-clauses]
[accessibility-modifiers] delegate result-type identifier
([formal-parameters]);
```

### <a name="parameters"></a>Parameter

*Attribute*  
(Optional) Zusätzliche deklarative Informationen. Weitere Informationen zu Attributen und Attributklassen finden Sie unter "Attribute".

*type-parameter-identifier(s)*  
Durch Trennzeichen getrennte Liste der Bezeichner für die Typparameter an.

*Type-Parameter-Einschränkungen-Klauseln*  
Nimmt die Form, die im angegebenen [Einschränkungen für generische Typparameter (C++ / CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)

*Zugriffsmodifizierer*  
(Optional) Zugriffsmodifizierer (z. B. **öffentliche**, **private**).

*result-type*  
Der Rückgabetyp des Delegaten.

*identifier*  
Der Name des Delegaten.

*Formal-parameters*  
(Optional) Die Parameterliste des Delegaten.

## <a name="example"></a>Beispiel

Die Typparameter des Delegaten werden die zum Zeitpunkt angegeben, in ein Delegatobjekt erstellt wird. Sowohl der Delegat als auch die Methode, die zugeordnet müssen die gleiche Signatur aufweisen. Folgendes ist ein Beispiel für eine Deklaration einer generischen Delegaten.

```cpp
// generics_generic_delegate1.cpp
// compile with: /clr /c
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, dass

- Sie können nicht das gleiche Delegatobjekt mit unterschiedlichen konstruierte Typen verwenden. Erstellen von anderen Delegaten Objekte für verschiedene Arten.

- Ein generischer Delegat kann eine generische Methode zugeordnet werden.

- Wenn eine generische Methode ohne Angabe von Typargumenten aufgerufen wird, versucht der Compiler die Typargumente für den Aufruf abzuleiten.

```cpp
// generics_generic_delegate2.cpp
// compile with: /clr
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);

generic <class ItemType>
ref struct MyGenClass {
   ItemType MyMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

ref struct MyClass {
   generic <class ItemType>
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

Das folgende Beispiel deklariert einen generischen Delegaten `GenDelegate<ItemType>`, und klicken Sie dann durch Zuordnen der Methode instanziiert wird `MyMethod` , verwendet den Typparameter `ItemType`. Zwei Instanzen von Delegaten (Integer und Double) erstellt und aufgerufen.

```cpp
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