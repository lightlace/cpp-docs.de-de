---
title: Compilerfehler C2974
ms.date: 11/04/2016
f1_keywords:
- C2974
helpviewer_keywords:
- C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
ms.openlocfilehash: 2fa0fae07435f3ab63398b7b3f02f9c662e7b436
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501373"
---
# <a name="compiler-error-c2974"></a>Compilerfehler C2974

Ungültiger Typ das Argument "Zahl", erwartet wurde der Typ

Das generische oder Vorlagenklasse Argument entspricht nicht der generische oder Vorlagendeklaration. Ein Typ sollte in spitzen Klammern angezeigt werden. Überprüfen Sie die generische oder Vorlagenklasse Definition so, dass die richtigen Typen zu ermitteln.

Im folgende Beispiel wird die C2974 generiert:

```
// C2974.cpp
// C2974 expected
template <class T>
struct TC {};

template <typename T>
void tf(T){}

int main() {
   // Delete the following 2 lines to resolve
   TC<1>* tc;
   tf<"abc">("abc");

   TC<int>* tc;
   tf<const char *>("abc");
}
```

C2974 kann auch auftreten, wenn Generika verwendet werden:

```
// C2974b.cpp
// compile with: /clr
// C2974 expected
using namespace System;
generic <class T>
ref struct GCtype {};

generic <typename T>
void gf(T){}

int main() {
   // Delete the following 2 lines to resolve
   GCtype<"a">^ gc;
   gf<"a">("abc");

   // OK
   GCtype<int>^ gc;
   gf<String ^>("abc");
}
```