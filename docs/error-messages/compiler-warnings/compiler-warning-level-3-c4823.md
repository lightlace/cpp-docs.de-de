---
title: Compilerwarnung (Stufe 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: 28d490c341c4d14c2e6c03e13007b5a8be423622
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401539"
---
# <a name="compiler-warning-level-3-c4823"></a>Compilerwarnung (Stufe 3) C4823

'Funktion': verwendet, die feste Zeigern, die Entladesemantik ist aber nicht aktiviert. Erwägen Sie die Verwendung von/EHa

Um ein Objekt auf dem verwalteten Heap verweist ein fester Zeiger deklariert, die in einem Blockbereich lösen zu können, wird der Compiler das Verhalten von Destruktoren für lokale Klassen, die "als", ob der feste Zeiger einen Destruktor enthält, der den Zeiger hebt simuliert. Um einen Aufruf von einem Destruktor nach dem Auslösen einer Ausnahme zu aktivieren, müssen Sie aktivieren Objekt entladen zu können, wozu können Sie [/EHsc](../../build/reference/eh-exception-handling-model.md).

Sie können auch manuell lösen das Objekt und die Warnung ignorieren.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4823 generiert.

```
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
