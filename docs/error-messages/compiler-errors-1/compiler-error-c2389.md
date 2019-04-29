---
title: Compilerfehler C2389
ms.date: 11/04/2016
f1_keywords:
- C2389
helpviewer_keywords:
- C2389
ms.assetid: 6122dc81-4ee3-49a5-a67d-d867808c9bac
ms.openlocfilehash: cb58ed0af3fda7ecbf399ac37758a688f014b826
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393648"
---
# <a name="compiler-error-c2389"></a>Compilerfehler C2389

'Operator': Ungültiger nullptr-Operand.

`nullptr` kann ein Operand sein.

Im folgenden Beispiel wird C2389 generiert:

```
// C2389.cpp
// compile with: /clr
int main() {
   throw nullptr;   // C2389
}
```