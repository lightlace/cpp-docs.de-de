---
title: Compilerfehler C2245
ms.date: 11/04/2016
f1_keywords:
- C2245
helpviewer_keywords:
- C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
ms.openlocfilehash: bc3f8e17d8d3746bdc243193f1349939bca5e164
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759203"
---
# <a name="compiler-error-c2245"></a>Compilerfehler C2245

Nicht vorhandene Memberfunktion "Funktion" wurde als Friend angegeben (Memberfunktionssignatur stimmt nicht mit Überladungen überein)

Eine als Friend angegebene Funktion wurde vom Compiler nicht gefunden.

Im folgenden Beispiel wird C2245 generiert:

```cpp
// C2245.cpp
// compile with: /c
class B {
   void f(int i);
};

class A {
   int m_i;
   friend void B::f(char);   // C2245
   // try the following line instead
   // friend void B::f(int);
};

void B::f(int i) {
   A a;
   a.m_i = 0;
}
```
