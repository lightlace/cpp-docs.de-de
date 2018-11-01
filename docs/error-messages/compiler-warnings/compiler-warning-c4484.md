---
title: Compilerwarnung C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 71a3d903ba32fecac4b2d8bfc3e0a93f19d0f4ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473170"
---
# <a name="compiler-warning-c4484"></a>Compilerwarnung C4484

'Überschreibungsfunktion': Basismethode der Verweisklasse-Methode, Klasse 'Basisklassenfunktion' entspricht, ist jedoch nicht gekennzeichnet 'virtual', 'new' oder 'override'; "new" (und nicht "virtual") wird angenommen.

Beim Kompilieren mit **"/ CLR"**, wird nicht vom Compiler implizit für eine Funktion, Klasse, die bedeutet, dass die Funktion wird einen neuen Slot in Vtable überschrieben. Um zu beheben, geben Sie explizit an, ob eine Funktion eine Überschreibung darstellt.

Weitere Informationen finden Sie unter:

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../windows/override-cpp-component-extensions.md)

- [New (neuer Slot in Vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)

C4484 wird immer als Fehler ausgegeben. Verwenden der [Warnung](../../preprocessor/warning.md) Pragma C4484 zu unterdrücken.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4484 generiert.

```
// C4484.cpp
// compile with: /clr
ref struct A {
   virtual void Test() {}
};

ref struct B : A {
   void Test() {}   // C4484
};

// OK
ref struct C {
   virtual void Test() {}
   virtual void Test2() {}
};

ref struct D : C {
   virtual void Test() new {}
   virtual void Test2() override {}
};
```