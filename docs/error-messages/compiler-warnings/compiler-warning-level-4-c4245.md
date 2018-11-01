---
title: Compilerwarnung (Stufe 4) C4245
ms.date: 11/04/2016
f1_keywords:
- C4245
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
ms.openlocfilehash: 7f22386439803de1b59f3236775aa6cec0254eab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436802"
---
# <a name="compiler-warning-level-4-c4245"></a>Compilerwarnung (Stufe 4) C4245

'Konvertierung': Konvertierung von 'type1' in 'type2', signed/unsigned-Konflikt

Sie haben versucht, eine signierte konvertieren **const** , die auf einen negativen Wert hat eine `unsigned`.

Im folgende Beispiel wird die C4245 generiert:

```
// C4245.cpp
// compile with: /W4 /c
const int i = -1;
unsigned int j = i; // C4245

const int k = 1;
unsigned int l = k; // okay

int m = -1;
unsigned int n = m; // okay

void Test(size_t i) {}

int main() {
   Test( -19 );   // C4245
}
```