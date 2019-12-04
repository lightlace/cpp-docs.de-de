---
title: Compilerfehler C2106
ms.date: 11/04/2016
f1_keywords:
- C2106
helpviewer_keywords:
- C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
ms.openlocfilehash: baa0307dcf5d68a9ca26414b6f48e95289958a96
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752040"
---
# <a name="compiler-error-c2106"></a>Compilerfehler C2106

"Operator": der linke Operand muss ein l-Wert sein.

Der Operator muss über einen l-Wert als linken Operanden verfügen.

Im folgenden Beispiel wird C2106 generiert:

```cpp
// C2106.cpp
int main() {
   int a;
   1 = a;   // C2106
   a = 1;   // OK
}
```
