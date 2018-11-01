---
title: Compilerfehler C2140
ms.date: 11/04/2016
f1_keywords:
- C2140
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
ms.openlocfilehash: e04a44007161fcfae5bab948584809590edbc095
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668701"
---
# <a name="compiler-error-c2140"></a>Compilerfehler C2140

'Typ': ein Typ, der einen generischen Typparameter abhängig ist, ist als Argument für das systeminterne Typmerkmal 'Eigenschaft' des Compilers nicht zulässig

Eine Typeigenschaft wurde ein ungültiger Typbezeichner übergeben.

Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2140 generiert.

```
// C2140.cpp
// compile with: /clr /c
template <class T>

struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class x {};

generic <class T>
ref class C {
   void f() {
      System::Console::WriteLine(__is_polymorphic(T));   // C2140
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140

      System::Console::WriteLine(__is_polymorphic(x));   // OK
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK
   }
};
```