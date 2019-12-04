---
title: Compilerfehler C2706
ms.date: 11/04/2016
f1_keywords:
- C2706
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
ms.openlocfilehash: bca86d3c0cf886c64a1d668468c793d0e77b2867
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757461"
---
# <a name="compiler-error-c2706"></a>Compilerfehler C2706

Ungültige __except ohne übereinstimmende \__try (fehlendes '} ' in \__try Block?)

Der Compiler hat keine schließende geschweifte Klammer für einen `__try`-Block gefunden.

Im folgenden Beispiel wird C2706 generiert:

```cpp
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```
