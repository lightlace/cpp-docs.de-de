---
title: Compilerwarnung (Stufe 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: 1583da44368225eabd8181be970f69f6582111e1
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2019
ms.locfileid: "74682978"
---
# <a name="compiler-warning-level-4-c4487"></a>Compilerwarnung (Stufe 4) C4487

"derived_class_function": stimmt mit der geerbten nicht virtuellen Methode "base_class_function" überein, ist jedoch nicht explizit als "New" markiert.

Eine Funktion in einer abgeleiteten Klasse verfügt über dieselbe Signatur wie eine nicht virtuelle Basisklassen Funktion. C4487 erinnert Sie daran, dass die Funktion der abgeleiteten Klasse die Basisklassen Funktion nicht außer Kraft setzt. Markieren Sie die Funktion der abgeleiteten Klasse explizit als `new`, um diese Warnung zu beheben.

Weitere Informationen finden Sie unter [New (neuer Slot in Vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4487 generiert.

```cpp
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```