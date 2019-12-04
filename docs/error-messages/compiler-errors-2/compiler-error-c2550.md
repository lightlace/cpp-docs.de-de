---
title: Compilerfehler C2550
ms.date: 11/04/2016
f1_keywords:
- C2550
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
ms.openlocfilehash: 29e907e682e0caae86569fe8bd7c101b3e0b14a3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740818"
---
# <a name="compiler-error-c2550"></a>Compilerfehler C2550

' Identifier ': konstruktorinitialisiererlisten sind nur für konstruktordefinitionen zulässig.

Eine basisklasseninitialisiererliste wird für die Definition einer Funktion verwendet, bei der es sich nicht um einen Konstruktor handelt.

Im folgenden Beispiel wird C2550 generiert:

```cpp
// C2550.cpp
// compile with: /c
class C {
public:
   C();
};

class D : public C {
public:
   D();
   void func();
};

void D::func() : C() {}  // C2550
D::D() : C() {}   // OK
```
