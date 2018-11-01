---
title: Compilerfehler C3650
ms.date: 11/04/2016
f1_keywords:
- C3650
helpviewer_keywords:
- C3650
ms.assetid: ca4d8de4-b027-4d13-9b9f-03ca62905c33
ms.openlocfilehash: 52d30f3ddee8b25ea54e799cfcb984bdffa80726
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508870"
---
# <a name="compiler-error-c3650"></a>Compilerfehler C3650

'Schnittstellenmethode': kann nicht als explizite Überschreibung verwendet werden, muss eine virtuelle Memberfunktion einer Basisklasse

Es wurde versucht, eine explizite Überschreibung für ein Element ausführen, die nicht virtuelle war.

Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).

Im folgende Beispiel wird die C3650 generiert:

```
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