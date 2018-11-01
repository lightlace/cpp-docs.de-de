---
title: Compilerfehler C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 581aae7e1f979b3dd39caf2ce3d263fdb856c56a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543775"
---
# <a name="compiler-error-c3628"></a>Compilerfehler C3628

'base Class': verwaltete oder WinRTclasses unterstützen nur öffentliche Vererbung

Es wurde versucht, mit einer verwalteten oder WinRT Klasse als eine [private](../../cpp/private-cpp.md) oder [geschützt](../../cpp/protected-cpp.md) Basisklasse. Eine verwaltete oder WinRT-Klasse kann nur verwendet werden, als eine Basisklasse mit [öffentliche](../../cpp/public-cpp.md) Zugriff.

Im folgenden Beispiel wird C3628 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
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
