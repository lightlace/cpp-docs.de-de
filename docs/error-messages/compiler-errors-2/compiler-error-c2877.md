---
title: Compilerfehler C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: 093efbf0c329967983c1808ee46011425745515f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595801"
---
# <a name="compiler-error-c2877"></a>Compilerfehler C2877

'Symbol' kann nicht zugegriffen werden, von "Klasse"

Alle Elemente, die von einer Basisklasse abgeleitet, muss in der abgeleiteten Klasse zugegriffen werden kann.

Im folgende Beispiel wird die C2877 generiert:

```
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```