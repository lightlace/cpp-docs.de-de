---
title: Compilerfehler C2783
ms.date: 11/04/2016
f1_keywords:
- C2783
helpviewer_keywords:
- C2783
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
ms.openlocfilehash: adba87853bac764d4975d6b6fa9aa44940ced03c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739674"
---
# <a name="compiler-error-c2783"></a>Compilerfehler C2783

' Deklaration ': das Vorlagen Argument für ' Identifier ' konnte nicht abgeleitet werden.

Der Compiler kann ein Vorlagen Argument nicht ermitteln. Standardargumente können nicht zum Ableiten eines Vorlagen Arguments verwendet werden.

Im folgenden Beispiel wird C2783 generiert:

```cpp
// C2783.cpp
template<typename T1, typename T2>
T1 f(T2) {
   return 248;
}

int main() {
   f(1);   // C2783
   // try the following line instead
   int i = f<int>(1);
}
```

C2783 kann auch auftreten, wenn Generika verwendet werden:

```cpp
// C2783b.cpp
// compile with: /clr
using namespace System;
generic<typename T1, typename T2>
T1 gf(T2) {
   T1 t1 = safe_cast<T1>( Activator::CreateInstance(T1::typeid));
   return t1;
}

ref class MyClass{};

int main() {
   int i;
   i = gf(9);   // C2783

   // OK
   i = gf<int>(9);
}
```
