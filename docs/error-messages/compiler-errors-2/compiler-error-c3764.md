---
title: Compilerfehler C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 3ede846c9068978ad5d283e97b1c96d3527bf67c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757232"
---
# <a name="compiler-error-c3764"></a>Compilerfehler C3764

' override_function ': die Basisklassen Methode ' Base_class_function ' kann nicht überschrieben werden.

Der Compiler hat eine falsch formatierte außer Kraft Setzung erkannt. Beispielsweise wurde die Basisklassen Funktion nicht `virtual`. Weitere Informationen finden Sie unter [außer Kraft](../../extensions/override-cpp-component-extensions.md)Setzung.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3764 generiert.

```cpp
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>Beispiel

C3764 kann auch auftreten, wenn eine Basisklassen Methode explizit und überschrieben wurde. Im folgenden Beispiel wird C3764 generiert.

```cpp
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```
