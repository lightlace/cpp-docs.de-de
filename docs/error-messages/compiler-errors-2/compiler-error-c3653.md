---
title: Compilerfehler C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 69fc6fa9303b2256172dd079028050823f053246
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756331"
---
# <a name="compiler-error-c3653"></a>Compilerfehler C3653

"Function": kann nicht als benannte außer Kraft Setzung verwendet werden: eine Funktion, die überschrieben wird, wurde nicht gefunden. haben Sie vergessen, die Funktion explizit zu benennen, indem Sie einen::-Operator verwenden?

Eine explizite Überschreibung hat eine Funktion angegeben, die in keiner Schnittstelle gefunden wurde. Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md)schreibungen.

Im folgenden Beispiel wird C3653 generiert:

```cpp
// C3653.cpp
// compile with: /clr
public interface struct I {
   void h();
};

public ref struct X : public I {
   virtual void f() new sealed = J {};   // C3653 no J in scope
   virtual void g() {}   // OK
   virtual void h() new sealed = I::h {};   // OK
};
```
