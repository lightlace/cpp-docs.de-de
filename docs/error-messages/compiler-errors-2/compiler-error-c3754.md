---
title: Compilerfehler C3754
ms.date: 11/04/2016
f1_keywords:
- C3754
helpviewer_keywords:
- C3754
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
ms.openlocfilehash: 65b6a24c47df5fc40f0305de4890c2ef2bc3c28b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757292"
---
# <a name="compiler-error-c3754"></a>Compilerfehler C3754

Delegatkonstruktor: die Member-Funktion "Function" kann nicht für eine Instanz vom Typ "Type" aufgerufen werden.

Eine Funktion wurde durch einen Zeiger auf einen Typ aufgerufen, der die Funktion nicht enthält.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3754 generiert:

```cpp
// C3754a.cpp
// compile with: /clr
using namespace System;

delegate void MyDel();

interface class MyInterface {};

ref struct MyClass : MyInterface {
   void f() {}
};

int main() {
   MyInterface^ p = gcnew MyClass;
   MyDel^ q = gcnew MyDel(p, &MyClass::f);   // C3754
   // try the following line instead
//   MyDel^ q = gcnew MyDel(safe_cast<MyClass^>(p), &MyClass::f);
}
```
