---
title: Compilerwarnung (Stufe 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: a96877252b0b7699f5e4033f8e695f4d9016a6c9
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541267"
---
# <a name="compiler-warning-level-3-c4823"></a>Compilerwarnung (Stufe 3) C4823

"Function": verwendet anheften-Zeiger, aber die Entlade Semantik ist nicht aktiviert. Verwenden Sie/EHA.

Um ein Objekt auf dem verwalteten Heap aufzulösen, auf das von einem Fixierungs Zeiger verwiesen wird, der in einem Block Bereich deklariert wurde, simuliert der Compiler das Verhalten von Debuggern von lokalen Klassen, wobei der angeheftete Zeiger einen Dekonstruktor aufweist, der den Zeiger nulliert. Zum Aktivieren eines Aufrufers nach dem Auslösen einer Ausnahme müssen Sie die Objekt Auflösung aktivieren, was Sie mithilfe von [/EHsc](../../build/reference/eh-exception-handling-model.md)tun können.

Sie können das Objekt auch manuell lösen und die Warnung ignorieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4823 generiert.

```cpp
// C4823.cpp
// compile with: /clr /W3 /EHa-
using namespace System;

ref struct G {
   int m;
};

void f(G ^ pG) {
   try {
      pin_ptr<int> p = &pG->m;
      // manually unpin, ignore warning
      // p = nullptr;
      throw gcnew Exception;
   }
   catch(Exception ^) {}
}   // C4823 warning

int main() {
   f( gcnew G );
}
```
