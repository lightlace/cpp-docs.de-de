---
title: Compilerfehler C3650
ms.date: 11/04/2016
f1_keywords:
- C3650
helpviewer_keywords:
- C3650
ms.assetid: ca4d8de4-b027-4d13-9b9f-03ca62905c33
ms.openlocfilehash: 2b1b769ed7e27e9c8c3edbe6b08452f3ec964727
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756356"
---
# <a name="compiler-error-c3650"></a>Compilerfehler C3650

"Interface_method": kann nicht als explizite Überschreibung verwendet werden, muss eine virtuelle Member-Funktion einer Basisklasse sein.

Es wurde versucht, eine explizite außer Kraft setzung für einen Member auszuführen, der nicht virtuell war.

Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md)schreibungen.

Im folgenden Beispiel wird C3650 generiert:

```cpp
// C3650.cpp
// compile with: /clr
public interface struct I {
   void a();
};

public ref class S {
public:
   static int f() { return 0; }
   static int g() { return 0; }
};

public ref struct T1 : public S, I {
   virtual int f() new sealed = S::f;   // C3650
   virtual int g() { return 0; }   // OK does not override S::g
   virtual void a() new sealed = I::a {}   // OK
};
```
