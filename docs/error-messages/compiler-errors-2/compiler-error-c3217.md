---
title: Compilerfehler C3217
ms.date: 11/04/2016
f1_keywords:
- C3217
helpviewer_keywords:
- C3217
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
ms.openlocfilehash: cb837a42841b2695941d4cd6122d186665d2d7e2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754587"
---
# <a name="compiler-error-c3217"></a>Compilerfehler C3217

"param": Der generische Parameter kann in dieser Deklaration nicht eingeschränkt werden.

Eine Einschränkung war falsch formatiert. Der generische Einschränkungsparameter muss mit dem generischen Klassenvorlagenparameter übereinstimmen.

Im folgenden Beispiel wird C3217 generiert:

```cpp
// C3217.cpp
// compile with: /clr
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T : A   // C3217
   void f();
};
```

Das folgende Beispiel zeigt eine mögliche Lösung:

```cpp
// C3217b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T1 : A
   void f();
};
```
