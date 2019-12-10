---
title: Compilerwarnung (Stufe 4) C4245
ms.date: 11/04/2016
f1_keywords:
- C4245
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
ms.openlocfilehash: 321451f0cc2ac538dbd0779001e22be047a3cc4d
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991419"
---
# <a name="compiler-warning-level-4-c4245"></a>Compilerwarnung (Stufe 4) C4245

' Konvertierung ': Konvertierung von ' Typ1 ' in ' Typ2 ', nicht übereinstimmende/nicht signierte Konvertierung

Sie haben versucht, einen signierten **Konstanten** mit einem negativen Wert in eine `unsigned`zu konvertieren.

Im folgenden Beispiel wird C4245 generiert:

```cpp
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
