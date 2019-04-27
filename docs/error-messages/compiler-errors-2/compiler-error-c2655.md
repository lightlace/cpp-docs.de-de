---
title: Compilerfehler C2655
ms.date: 11/04/2016
f1_keywords:
- C2655
helpviewer_keywords:
- C2655
ms.assetid: beaefa6e-51b3-4df9-9150-960f3fbf40e0
ms.openlocfilehash: 094dabb5ad07796194ae391000ca1e9025602d93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161185"
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