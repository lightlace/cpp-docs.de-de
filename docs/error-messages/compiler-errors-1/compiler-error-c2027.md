---
title: Compilerfehler C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 62cf208d9d0025afba06d32a15b9a1e50777c473
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751000"
---
# <a name="compiler-error-c2027"></a>Compilerfehler C2027

Verwendung des nicht definierten Typs "Typ"

Ein Typ kann erst verwendet werden, nachdem er definiert wurde. Um den Fehler zu beheben, stellen Sie sicher, dass der Typ vollständig definiert ist, bevor Sie darauf verweisen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2027 generiert.

```cpp
// C2027.cpp
class C;
class D {
public:
   void func() {
   }
};

int main() {
   C *pC;
   pC->func();   // C2027

   D *pD;
   pD->func();
}
```

## <a name="example"></a>Beispiel

Es ist möglich, einen Zeiger auf einen deklarierten, aber nicht definierten Typ zu deklarieren. Lässt C++ jedoch keinen Verweis auf einen nicht definierten Typ zu.

Im folgenden Beispiel wird C2027 generiert.

```cpp
// C2027_b.cpp
class A;
A& CreateA();

class B;
B* CreateB();

int main() {
   CreateA();   // C2027
   CreateB();   // OK
}
```
