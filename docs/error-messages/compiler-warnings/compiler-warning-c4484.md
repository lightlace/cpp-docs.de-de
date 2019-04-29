---
title: Compilerwarnung C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 29e99da02aa0144699d3c20e523b5e5e4b6b8f72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363530"
---
# <a name="compiler-warning-c4484"></a>Compilerwarnung C4484

'Überschreibungsfunktion': Basismethode der Verweisklasse-Methode, Klasse 'Basisklassenfunktion' entspricht, ist jedoch nicht gekennzeichnet 'virtual', 'new' oder 'override'; "new" (und nicht "virtual") wird angenommen.

Beim Kompilieren mit **"/ CLR"**, wird nicht vom Compiler implizit für eine Funktion, Klasse, die bedeutet, dass die Funktion wird einen neuen Slot in Vtable überschrieben. Um zu beheben, geben Sie explizit an, ob eine Funktion eine Überschreibung darstellt.

Weitere Informationen finden Sie unter:

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../extensions/override-cpp-component-extensions.md)

- [new (neuer Slot in vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

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