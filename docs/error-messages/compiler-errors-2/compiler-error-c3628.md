---
title: Compilerfehler C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 9976cb2425f8f855ffb2903c07de22822c781e20
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755823"
---
# <a name="compiler-error-c3628"></a>Compilerfehler C3628

' Basisklasse ': verwaltete oder winrtclasses unterstützen nur die öffentliche Vererbung.

Es wurde versucht, eine verwaltete oder WinRT-Klasse als [private](../../cpp/private-cpp.md) oder [geschützte](../../cpp/protected-cpp.md) Basisklasse zu verwenden. Eine verwaltete oder WinRT-Klasse kann nur als Basisklasse mit [öffentlichem](../../cpp/public-cpp.md) Zugriff verwendet werden.

Im folgenden Beispiel wird C3628 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
