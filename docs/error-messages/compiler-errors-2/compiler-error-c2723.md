---
title: Compilerfehler C2723
ms.date: 11/04/2016
f1_keywords:
- C2723
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
ms.openlocfilehash: bc07a99f12ed0e447427990969e54f7f3d3d3b7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383021"
---
# <a name="compiler-error-c2723"></a>Compilerfehler C2723

„Funktion“: Spezifizierer „Spezifizierer“ ist in Funktionsdefinition unzulässig.

Der Spezifizierer darf nicht mit einer Funktionsdefinition außerhalb einer Klassendeklaration vorkommen. Der `virtual`-Spezifizierer kann nur in einer Deklaration einer Memberfunktion innerhalb einer Klassendeklaration angegeben werden.

Im folgenden Beispiel wird C2723 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2723.cpp
struct X {
   virtual void f();
   virtual void g();
};

virtual void X::f() {}   // C2723

// try the following line instead
void X::g() {}
```