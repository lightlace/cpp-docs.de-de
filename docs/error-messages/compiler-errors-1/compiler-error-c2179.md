---
title: Compilerfehler C2179
ms.date: 11/04/2016
f1_keywords:
- C2179
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
ms.openlocfilehash: 5b9b5382ab934f8d870e58189a447775a1e9a415
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737165"
---
# <a name="compiler-error-c2179"></a>Compilerfehler C2179

' type ': ein Attribut Argument kann keine Typparameter verwenden.

Ein generischer Typparameter wird zur Laufzeit aufgelöst. Ein Attribut Parameter muss jedoch zur Kompilierzeit aufgelöst werden. Daher können Sie keinen generischen Typparameter als Argument für ein Attribut verwenden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2179 generiert.

```cpp
// C2179.cpp
// compile with: /clr
using namespace System;

public ref struct Attr : Attribute {
   Attr(Type ^ a) {
      x = a;
   }

   Type ^ x;
};

ref struct G {};

generic<typename T>
public ref class Z {
public:
   Type ^ d;
   [Attr(T::typeid)]   // C2179
   // try the following line instead
   // [Attr(G::typeid)]
   T t;
};
```
