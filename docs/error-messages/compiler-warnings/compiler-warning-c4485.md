---
title: Compilerwarnung C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: b5afb829485e0e9533a14e818e6d6785f268a83b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311315"
---
# <a name="compiler-warning-c4485"></a>Compilerwarnung C4485

'Überschreibungsfunktion': entspricht der Klassenmethode "Basisklassenfunktion" Basismethode der Verweisklasse ist allerdings nicht markierte 'new' oder 'override'; "new" (und "virtual") werden angenommen.

Überschreibt ein Accessor, mit oder ohne die `virtual` -Schlüsselwort, eine Basisklasse Accessor-Funktion, aber die `override` oder `new` Spezifizierer war nicht Teil der überschreibenden Funktionssignatur. Hinzufügen der `new` oder `override` Spezifizierer, um diese Warnung zu beheben.

Finden Sie unter [überschreiben](../../extensions/override-cpp-component-extensions.md) und [new (neuer Slot in Vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) für Weitere Informationen.

C4485 wird immer als Fehler ausgegeben. Verwenden der [Warnung](../../preprocessor/warning.md) Pragma C4485 zu unterdrücken.

## <a name="example"></a>Beispiel

Das folgende Beispiel generiert C4485

```
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```