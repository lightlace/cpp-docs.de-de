---
title: Compilerfehler C2655
ms.date: 11/04/2016
f1_keywords:
- C2655
helpviewer_keywords:
- C2655
ms.assetid: beaefa6e-51b3-4df9-9150-960f3fbf40e0
ms.openlocfilehash: 094dabb5ad07796194ae391000ca1e9025602d93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506768"
---
# <a name="compiler-error-c2655"></a>Compilerfehler C2655

'Bezeichner': Definition oder Neudeklaration im aktuellen Gültigkeitsbereich unzulässig

Ein Bezeichner kann nur im globalen Gültigkeitsbereich erneut deklariert werden.

Im folgende Beispiel wird die C2655 generiert:

```
// C2655.cpp
class A {};
class B {
public:
   static int i;
};

int B::i;  // OK

int main() {
   A B::i;  // C2655
}
```