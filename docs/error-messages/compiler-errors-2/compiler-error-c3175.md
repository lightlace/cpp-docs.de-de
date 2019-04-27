---
title: Compilerfehler C3175
ms.date: 11/04/2016
f1_keywords:
- C3175
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
ms.openlocfilehash: 368e5a9cb9bea04a7889c25c86a7245049677112
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175460"
---
# <a name="compiler-error-c3175"></a>Compilerfehler C3175

"Funktion1": eine Methode eines verwalteten Typs kann nicht aufgerufen werden, von nicht verwalteten Funktion "Funktion2"

Nicht verwaltete Funktionen können keine Memberfunktionen von verwalteten Klassen aufrufen.

Im folgende Beispiel wird die C3175 generiert:

```
// C3175_2.cpp
// compile with: /clr

ref struct A {
   static void func() {
   }
};

#pragma unmanaged   // remove this line to resolve

void func2() {
   A::func();   // C3175
}

#pragma managed

int main() {
   A ^a = gcnew A;
   func2();
}
```
