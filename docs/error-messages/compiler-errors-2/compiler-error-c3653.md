---
title: Compilerfehler C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: d7936303dab4fbb273a01f98def5b9af99f89dac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477622"
---
# <a name="compiler-error-c3653"></a>Compilerfehler C3653

'Funktion': kann nicht als benannte Überschreibung verwendet werden: eine Funktion, die überschrieben wurde nicht gefunden; haben Sie vergessen, auf den Funktionsnamen explizit mithilfe einer:: Operator?

Eine explizite Überschreibung angegeben, eine Funktion, die nicht in einer beliebigen Schnittstelle gefunden wurde. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3653 generiert:

```
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