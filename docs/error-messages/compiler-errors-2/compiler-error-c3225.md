---
title: Compilerfehler C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: 1caa1e7ce787ffc14e615c946b5d670c75e0332a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757617"
---
# <a name="compiler-error-c3225"></a>Compilerfehler C3225

das generische Typargument für ' arg ' kann nicht ' type ' sein, es muss ein Werttyp oder ein behandlertyp sein.

Das generische Typargument war nicht vom richtigen Typ.

Weitere Informationen finden Sie unter [Generics](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Es ist nicht möglich, einen generischen Typ mit einem systemeigenen Typ zu instanziieren. Im folgenden Beispiel wird C3225 generiert.

```cpp
// C3225.cpp
// compile with: /clr
class A {};

ref class B {};

generic <class T>
ref class C {};

int main() {
   C<A>^ c = gcnew C<A>;   // C3225
   C<B^>^ c2 = gcnew C<B^>;   // OK
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine-Komponente C#mithilfe von erstellt. Beachten Sie, dass die-Einschränkung angibt, dass der generische Typ nur mit einem Werttyp instanziiert werden kann.

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

## <a name="example"></a>Beispiel

In diesem Beispiel wird C#die-erstellte Komponente verwendet und verstößt gegen die Einschränkung, dass myList nur mit einem anderen Werttyp als <xref:System.Nullable>instanziiert werden kann. Im folgenden Beispiel wird C3225 generiert.

```cpp
// C3225_c.cpp
// compile with: /clr
#using "C3225_b.dll"
ref class A {};
value class B {};
int main() {
   MyList<A> x;   // C3225
   MyList<B> y;   // OK
}
```
