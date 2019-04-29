---
title: Compilerfehler C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 2570ee9abb148b919242de7786cd6fa91765286f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400252"
---
# <a name="compiler-error-c3764"></a>Compilerfehler C3764

'Überschreibungsfunktion': kann nicht "Basisklassenfunktion" für die Methode der Basisklasse überschreiben

Der Compiler hat ein falsch formatiertes außer Kraft setzen. Zum Beispiel wurde die Funktion der Basisklasse nicht `virtual`. Weitere Informationen finden Sie unter [überschreiben](../../extensions/override-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3764 generiert.

```
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>Beispiel

C3764 kann auch auftreten, wenn eine Basisklasse-Methode, die sowohl explizit ist, und mit dem Namen außer Kraft gesetzt. Im folgende Beispiel wird die C3764 generiert.

```
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```