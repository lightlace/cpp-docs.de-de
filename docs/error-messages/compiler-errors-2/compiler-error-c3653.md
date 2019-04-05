---
title: Compilerfehler C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 75e2c061190b24019491db7a625ecafb5ac82b6b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776647"
---
# <a name="compiler-error-c3653"></a>Compilerfehler C3653

'Funktion': kann nicht als benannte Überschreibung verwendet werden: eine Funktion, die überschrieben wurde nicht gefunden; haben Sie vergessen, auf den Funktionsnamen explizit mithilfe einer:: Operator?

Eine explizite Überschreibung angegeben, eine Funktion, die nicht in einer beliebigen Schnittstelle gefunden wurde. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../extensions/explicit-overrides-cpp-component-extensions.md).

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